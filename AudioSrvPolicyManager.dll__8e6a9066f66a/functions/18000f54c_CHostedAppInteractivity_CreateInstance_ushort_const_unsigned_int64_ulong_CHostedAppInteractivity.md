# CHostedAppInteractivity::CreateInstance(ushort const *,unsigned __int64,ulong,CHostedAppInteractivity * *)

- ea: `0x18000f54c`
- end: `0x18000f5ec`
- name: `?CreateInstance@CHostedAppInteractivity@@SAJPEBG_KKPEAPEAV1@@Z`
- size: `160`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned int, struct CHostedAppInteractivity **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18002174c`

## callees

- `0x18000da80`
- `0x18000f54c`
- `0x18000f5f4`
- `0x180019ff0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f572`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f563`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f563`

## string_xrefs

- `0x18000f5a7`: `CHostedAppInteractivity::CreateInstance`

## pseudocode

```c
__int64 __fastcall CHostedAppInteractivity::CreateInstance(
        unsigned __int16 *a1,
        __int64 a2,
        int a3,
        struct CHostedAppInteractivity **a4)
{
  HANDLE ProcessHeap; // rax
  struct CHostedAppInteractivity *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct CHostedAppInteractivity *v12; // rbx
  unsigned int v13; // edi
  int v15; // eax
  unsigned int v16; // edx

  ProcessHeap = GetProcessHeap();
  v9 = (struct CHostedAppInteractivity *)HeapAlloc(ProcessHeap, 0, 0x18u);
  v12 = v9;
  if ( v9 )
  {
    *(_QWORD *)v9 = 0;
    *((_DWORD *)v9 + 2) = -1;
    *((_DWORD *)v9 + 3) = 0;
    *((_DWORD *)v9 + 2) = a3;
    *((_QWORD *)v9 + 2) = a2;
    v15 = _AllocString<CTCoAllocPolicy>(v11, v10, a1, v9);
    v13 = v15;
    if ( v15 >= 0 )
    {
      *a4 = v12;
      return v13;
    }
    CHostedAppInteractivity::`scalar deleting destructor'(v12, v16);
  }
  else
  {
    v13 = -2147024882;
  }
  AudPolicyLogError("CHostedAppInteractivity::CreateInstance", 313, v13);
  return v13;
}

```

## disassembly

```asm
0x18000f54c  push    rbx
0x18000f54e  push    rbp
0x18000f54f  push    rsi
0x18000f550  push    rdi
0x18000f551  push    r14
0x18000f553  sub     rsp, 30h
0x18000f557  mov     rsi, r9
0x18000f55a  mov     edi, r8d
0x18000f55d  mov     rbp, rdx
0x18000f560  mov     r14, rcx
0x18000f563  call    cs:__imp_GetProcessHeap
0x18000f569  xor     edx, edx; dwFlags
0x18000f56b  mov     rcx, rax; hHeap
0x18000f56e  lea     r8d, [rdx+18h]; dwBytes
0x18000f572  call    cs:__imp_HeapAlloc
0x18000f578  mov     [rsp+58h+var_38], rax
0x18000f57d  mov     rbx, rax
0x18000f580  test    rax, rax
0x18000f583  jz      short loc_18000F59F
0x18000f585  mov     qword ptr [rax], 0
0x18000f58c  mov     dword ptr [rax+8], 0FFFFFFFFh
0x18000f593  mov     dword ptr [rax+0Ch], 0
0x18000f59a  test    rax, rax
0x18000f59d  jnz     short loc_18000F5C5
0x18000f59f  mov     edi, 8007000Eh
0x18000f5a4  mov     r8d, edi; int
0x18000f5a7  lea     rcx, aChostedappinte_0; "CHostedAppInteractivity::CreateInstance"
0x18000f5ae  mov     edx, 139h; int
0x18000f5b3  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x18000f5b8  mov     eax, edi
0x18000f5ba  add     rsp, 30h
0x18000f5be  pop     r14
0x18000f5c0  pop     rdi
0x18000f5c1  pop     rsi
0x18000f5c2  pop     rbp
0x18000f5c3  pop     rbx
0x18000f5c4  retn
0x18000f5c5  mov     r9, rbx
0x18000f5c8  mov     [rax+8], edi
0x18000f5cb  mov     r8, r14
0x18000f5ce  mov     [rax+10h], rbp
0x18000f5d2  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18000f5d7  mov     edi, eax
0x18000f5d9  test    eax, eax
0x18000f5db  js      short loc_18000F5E2
0x18000f5dd  mov     [rsi], rbx
0x18000f5e0  jmp     short loc_18000F5B8
0x18000f5e2  mov     rcx, rbx; this
0x18000f5e5  call    ??_GCHostedAppInteractivity@@QEAAPEAXI@Z; CHostedAppInteractivity::`scalar deleting destructor'(uint)
0x18000f5ea  jmp     short loc_18000F5A4
```
