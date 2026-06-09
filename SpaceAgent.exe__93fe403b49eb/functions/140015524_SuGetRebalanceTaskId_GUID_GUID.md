# SuGetRebalanceTaskId(_GUID *,_GUID *)

- ea: `0x140015524`
- end: `0x1400155fc`
- name: `?SuGetRebalanceTaskId@@YAHPEAU_GUID@@0@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400188b0`

## callees

- `0x140015524`
- `0x1400198d4`
- `0x1400199d4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400155bc`
- `KERNEL32!LocalFree` at `0x1400155da`
- `KERNEL32!LocalFree` at `0x1400155e3`
- `KERNEL32!LocalFree` at `0x1400155bc`
- `KERNEL32!LocalFree` at `0x1400155da`
- `KERNEL32!LocalFree` at `0x1400155e3`
- `KERNEL32!GetLastError` at `0x140015597`
- `KERNEL32!GetLastError` at `0x140015597`

## pseudocode

```c
__int64 __fastcall SuGetRebalanceTaskId(struct _GUID *a1, struct _GUID *a2)
{
  HLOCAL v3; // rbx
  int TaskIds; // eax
  unsigned int *v6; // rbp
  unsigned int v7; // edi
  unsigned int i; // esi
  DWORD LastError; // eax
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF
  HLOCAL v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = 0;
  v3 = 0;
  *a2 = GUID_NULL;
  hMem = 0;
  TaskIds = SuGetTaskIds(a1, 0, (struct _SP_IDS **)&v12);
  v6 = (unsigned int *)v12;
  if ( TaskIds )
  {
    v7 = 1;
    for ( i = 0; i < *v6; ++i )
    {
      if ( (unsigned int)SuGetTask(a1, (struct _GUID *)&v6[4 * i + 1], (struct _SU_TASK_OBJECT **)&hMem) )
      {
        v3 = hMem;
        if ( *((_DWORD *)hMem + 161) == 3 )
        {
          *a2 = *(struct _GUID *)((char *)hMem + 56);
          break;
        }
        v3 = LocalFree(hMem);
        hMem = v3;
      }
      else
      {
        LastError = GetLastError();
        v3 = hMem;
        if ( LastError != 1168 )
          goto LABEL_2;
      }
    }
  }
  else
  {
LABEL_2:
    v7 = 0;
  }
  LocalFree(v6);
  LocalFree(v3);
  return v7;
}

```

## disassembly

```asm
0x140015524  mov     rax, rsp
0x140015527  mov     [rax+8], rbx
0x14001552b  push    rbp
0x14001552c  push    rsi
0x14001552d  push    rdi
0x14001552e  push    r14
0x140015530  push    r15
0x140015532  sub     rsp, 20h
0x140015536  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14001553d  mov     r14, rdx
0x140015540  mov     qword ptr [rax+18h], 0
0x140015548  xor     ebx, ebx
0x14001554a  lea     r8, [rax+18h]; struct _SP_IDS **
0x14001554e  movdqu  xmmword ptr [rdx], xmm0
0x140015552  xor     edx, edx; struct _GUID *
0x140015554  mov     [rax+10h], rbx
0x140015558  mov     r15, rcx
0x14001555b  call    ?SuGetTaskIds@@YAHPEAU_GUID@@0PEAPEAU_SP_IDS@@@Z; SuGetTaskIds(_GUID *,_GUID *,_SP_IDS * *)
0x140015560  mov     rbp, [rsp+48h+arg_10]
0x140015565  test    eax, eax
0x140015567  jnz     short loc_14001556D
0x140015569  xor     edi, edi
0x14001556b  jmp     short loc_1400155D7
0x14001556d  mov     edi, 1
0x140015572  xor     esi, esi
0x140015574  cmp     esi, [rbp+0]
0x140015577  jnb     short loc_1400155D7
0x140015579  mov     edx, esi
0x14001557b  lea     r8, [rsp+48h+hMem]; struct _SU_TASK_OBJECT **
0x140015580  shl     rdx, 4
0x140015584  mov     rcx, r15; struct _GUID *
0x140015587  add     rdx, 4
0x14001558b  add     rdx, rbp; struct _GUID *
0x14001558e  call    ?SuGetTask@@YAHPEAU_GUID@@0PEAPEAU_SU_TASK_OBJECT@@@Z; SuGetTask(_GUID *,_GUID *,_SU_TASK_OBJECT * *)
0x140015593  test    eax, eax
0x140015595  jnz     short loc_1400155AB
0x140015597  call    cs:__imp_GetLastError
0x14001559d  mov     rbx, [rsp+48h+hMem]
0x1400155a2  cmp     eax, 490h
0x1400155a7  jnz     short loc_140015569
0x1400155a9  jmp     short loc_1400155CA
0x1400155ab  mov     rbx, [rsp+48h+hMem]
0x1400155b0  cmp     dword ptr [rbx+284h], 3
0x1400155b7  jz      short loc_1400155CE
0x1400155b9  mov     rcx, rbx; hMem
0x1400155bc  call    cs:__imp_LocalFree
0x1400155c2  mov     rbx, rax
0x1400155c5  mov     [rsp+48h+hMem], rax
0x1400155ca  add     esi, edi
0x1400155cc  jmp     short loc_140015574
0x1400155ce  movups  xmm0, xmmword ptr [rbx+38h]
0x1400155d2  movdqu  xmmword ptr [r14], xmm0
0x1400155d7  mov     rcx, rbp; hMem
0x1400155da  call    cs:__imp_LocalFree
0x1400155e0  mov     rcx, rbx; hMem
0x1400155e3  call    cs:__imp_LocalFree
0x1400155e9  mov     rbx, [rsp+48h+arg_0]
0x1400155ee  mov     eax, edi
0x1400155f0  add     rsp, 20h
0x1400155f4  pop     r15
0x1400155f6  pop     r14
0x1400155f8  pop     rdi
0x1400155f9  pop     rsi
0x1400155fa  pop     rbp
0x1400155fb  retn
```
