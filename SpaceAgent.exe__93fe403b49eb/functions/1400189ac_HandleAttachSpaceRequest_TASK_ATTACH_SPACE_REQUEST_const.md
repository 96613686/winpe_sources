# HandleAttachSpaceRequest(TASK_ATTACH_SPACE_REQUEST const *)

- ea: `0x1400189ac`
- end: `0x140018a83`
- name: `?HandleAttachSpaceRequest@@YAHPEBUTASK_ATTACH_SPACE_REQUEST@@@Z`
- size: `215`
- prototype: `__int64 __fastcall(const struct TASK_ATTACH_SPACE_REQUEST *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140017d70`

## callees

- `0x140001caf`
- `0x140012e28`
- `0x1400166f8`
- `0x14001832c`
- `0x1400189ac`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140018a48`
- `KERNEL32!LocalFree` at `0x140018a48`
- `KERNEL32!SetLastError` at `0x1400189f8`
- `KERNEL32!SetLastError` at `0x140018a66`
- `KERNEL32!SetLastError` at `0x1400189f8`
- `KERNEL32!SetLastError` at `0x140018a66`
- `KERNEL32!GetLastError` at `0x140018a38`
- `KERNEL32!GetLastError` at `0x140018a5c`
- `KERNEL32!GetLastError` at `0x140018a38`
- `KERNEL32!GetLastError` at `0x140018a5c`

## pseudocode

```c
__int64 __fastcall HandleAttachSpaceRequest(const struct TASK_ATTACH_SPACE_REQUEST *a1)
{
  struct _SU_SPACE_OBJECT *v2; // rdi
  unsigned int v3; // ebx
  unsigned int v4; // r8d
  int SpaceFiltered; // eax
  DWORD LastError; // esi
  HLOCAL v7; // rax
  _BYTE v9[40]; // [rsp+20h] [rbp-B58h] BYREF
  __int128 v10; // [rsp+48h] [rbp-B30h]
  struct _SU_SPACE_OBJECT *v11; // [rsp+B88h] [rbp+10h] BYREF

  memset_0(v9, 0, 0xB48u);
  v2 = 0;
  v11 = 0;
  v3 = IssueProgressStringResult(32895);
  if ( v3 )
  {
    if ( *(_QWORD *)a1 == 48 )
    {
      v10 = *((_OWORD *)a1 + 1);
      SpaceFiltered = SuGetSpaceFiltered((struct _SU_POOL_OBJECT *)v9, (struct _GUID *)a1 + 2, v4, &v11);
      v2 = v11;
      v3 = SpaceFiltered;
      if ( SpaceFiltered )
        v3 = SuAttachSpaceEx(v11);
    }
    else
    {
      v3 = 0;
      SetLastError(0x18u);
    }
  }
  LastError = GetLastError();
  if ( v2 )
  {
    v7 = LocalFree(v2);
    if ( v3 )
    {
      v3 = v7 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v3;
}

```

## disassembly

```asm
0x1400189ac  mov     [rsp+arg_0], rbx
0x1400189b1  mov     [rsp+arg_10], rsi
0x1400189b6  push    rdi
0x1400189b7  sub     rsp, 0B70h
0x1400189be  mov     rsi, rcx
0x1400189c1  xor     edx, edx; Val
0x1400189c3  lea     rcx, [rsp+0B78h+var_B58]; void *
0x1400189c8  mov     r8d, 0B48h; Size
0x1400189ce  call    memset_0
0x1400189d3  xor     edi, edi
0x1400189d5  mov     ecx, 807Fh
0x1400189da  mov     [rsp+0B78h+arg_8], rdi
0x1400189e2  call    IssueProgressStringResult
0x1400189e7  mov     ebx, eax
0x1400189e9  test    eax, eax
0x1400189eb  jz      short loc_140018A38
0x1400189ed  cmp     qword ptr [rsi], 30h ; '0'
0x1400189f1  jz      short loc_140018A00
0x1400189f3  xor     ebx, ebx
0x1400189f5  lea     ecx, [rdi+18h]; dwErrCode
0x1400189f8  call    cs:__imp_SetLastError
0x1400189fe  jmp     short loc_140018A38
0x140018a00  movups  xmm0, xmmword ptr [rsi+10h]
0x140018a04  lea     rdx, [rsi+20h]; struct _GUID *
0x140018a08  lea     r9, [rsp+0B78h+arg_8]; struct _SU_SPACE_OBJECT **
0x140018a10  lea     rcx, [rsp+0B78h+var_B58]; struct _SU_POOL_OBJECT *
0x140018a15  movdqu  [rsp+0B78h+var_B30], xmm0
0x140018a1b  call    ?SuGetSpaceFiltered@@YAHPEAU_SU_POOL_OBJECT@@PEAU_GUID@@KPEAPEAU_SU_SPACE_OBJECT@@@Z; SuGetSpaceFiltered(_SU_POOL_OBJECT *,_GUID *,ulong,_SU_SPACE_OBJECT * *)
0x140018a20  mov     rdi, [rsp+0B78h+arg_8]
0x140018a28  mov     ebx, eax
0x140018a2a  test    eax, eax
0x140018a2c  jz      short loc_140018A38
0x140018a2e  mov     rcx, rdi; struct _SU_SPACE_OBJECT *
0x140018a31  call    ?SuAttachSpaceEx@@YAHPEAU_SU_SPACE_OBJECT@@@Z; SuAttachSpaceEx(_SU_SPACE_OBJECT *)
0x140018a36  mov     ebx, eax
0x140018a38  call    cs:__imp_GetLastError
0x140018a3e  mov     esi, eax
0x140018a40  test    rdi, rdi
0x140018a43  jz      short loc_140018A64
0x140018a45  mov     rcx, rdi; hMem
0x140018a48  call    cs:__imp_LocalFree
0x140018a4e  xor     ecx, ecx
0x140018a50  test    rax, rax
0x140018a53  setz    cl
0x140018a56  test    ebx, ebx
0x140018a58  jz      short loc_140018A64
0x140018a5a  mov     ebx, ecx
0x140018a5c  call    cs:__imp_GetLastError
0x140018a62  mov     esi, eax
0x140018a64  mov     ecx, esi; dwErrCode
0x140018a66  call    cs:__imp_SetLastError
0x140018a6c  lea     r11, [rsp+0B78h+var_8]
0x140018a74  mov     eax, ebx
0x140018a76  mov     rbx, [r11+10h]
0x140018a7a  mov     rsi, [r11+20h]
0x140018a7e  mov     rsp, r11
0x140018a81  pop     rdi
0x140018a82  retn
```
