# IsolationAwareImageList_Create

- ea: `0x18000e790`
- end: `0x18000e876`
- name: `IsolationAwareImageList_Create`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000dc60`

## callees

- `0x18000e604`
- `0x18000e790`
- `0x18000eaf0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e847`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f617`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f637`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e868`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f637`
- `KERNEL32!DeactivateActCtx` at `0x18000e85c`
- `KERNEL32!DeactivateActCtx` at `0x18000f62b`
- `KERNEL32!DeactivateActCtx` at `0x18000e85c`
- `KERNEL32!DeactivateActCtx` at `0x18000f62b`

## string_xrefs

- `0x18000e7e6`: `ImageList_Create`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_Create(unsigned int a1, unsigned int a2)
{
  __int64 v4; // rsi
  __int64 (__fastcall *v5)(_QWORD, _QWORD, __int64, __int64, int); // rbx
  __int64 v7; // rax
  int v8; // edi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+38h] [rbp-30h]

  v4 = 0;
  v11 = 0;
  v5 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, int))`IsolationAwareImageList_Create'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  if ( !v5 )
  {
    v7 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_Create");
    v5 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, int))v7;
    if ( !v7 )
    {
      v8 = 1;
      goto LABEL_10;
    }
    `IsolationAwareImageList_Create'::`2'::s_pfn = v7;
  }
  v8 = 1;
  v4 = v5(a1, a2, 33, 1, 1);
  v11 = v4;
LABEL_10:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v4 )
    {
      v8 = 0;
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v8 )
      SetLastError(LastError);
  }
  return v4;
}

```

## disassembly

```asm
0x18000e790  push    rbx
0x18000e792  push    rsi
0x18000e793  push    rdi
0x18000e794  push    r14
0x18000e796  push    r15
0x18000e798  sub     rsp, 40h
0x18000e79c  mov     r14d, edx
0x18000e79f  mov     r15d, ecx
0x18000e7a2  xor     esi, esi
0x18000e7a4  mov     [rsp+68h+var_30], rsi
0x18000e7a9  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x18000e7b0  mov     [rsp+68h+ulCookie], rsi
0x18000e7b5  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, esi
0x18000e7bb  jnz     short loc_18000E7E1
0x18000e7bd  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, esi
0x18000e7c3  jnz     short loc_18000E7E1
0x18000e7c5  lea     rcx, [rsp+68h+ulCookie]; lpCookie
0x18000e7ca  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000e7cf  test    eax, eax
0x18000e7d1  jnz     short loc_18000E7E1
0x18000e7d3  xor     eax, eax
0x18000e7d5  add     rsp, 40h
0x18000e7d9  pop     r15
0x18000e7db  pop     r14
0x18000e7dd  pop     rdi
0x18000e7de  pop     rsi
0x18000e7df  pop     rbx
0x18000e7e0  retn
0x18000e7e1  test    rbx, rbx
0x18000e7e4  jnz     short loc_18000E80A
0x18000e7e6  lea     rcx, aImagelistCreat; "ImageList_Create"
0x18000e7ed  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000e7f2  mov     rbx, rax
0x18000e7f5  test    rax, rax
0x18000e7f8  jz      short loc_18000E803
0x18000e7fa  mov     cs:?s_pfn@?1??IsolationAwareImageList_Create@@9@4P6APEAU_IMAGELIST@@HHIHH@ZEA, rax; _IMAGELIST * (*`IsolationAwareImageList_Create'::`2'::s_pfn)(int,int,uint,int,int)
0x18000e801  jmp     short loc_18000E80A
0x18000e803  mov     edi, 1
0x18000e808  jmp     short loc_18000E830
0x18000e80a  mov     edi, 1
0x18000e80f  mov     [rsp+68h+var_48], edi
0x18000e813  mov     r9d, edi
0x18000e816  lea     r8d, [rdi+20h]
0x18000e81a  mov     edx, r14d
0x18000e81d  mov     ecx, r15d
0x18000e820  mov     rax, rbx
0x18000e823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e828  mov     rsi, rax
0x18000e82b  mov     [rsp+68h+var_30], rax
0x18000e830  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e837  jz      short loc_18000E842
0x18000e839  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e840  jnz     short loc_18000E86E
0x18000e842  test    rsi, rsi
0x18000e845  jnz     short loc_18000E851
0x18000e847  call    cs:__imp_GetLastError
0x18000e84d  mov     ebx, eax
0x18000e84f  jmp     short loc_18000E855
0x18000e851  xor     edi, edi
0x18000e853  xor     ebx, ebx
0x18000e855  mov     rdx, [rsp+68h+ulCookie]; ulCookie
0x18000e85a  xor     ecx, ecx; dwFlags
0x18000e85c  call    cs:__imp_DeactivateActCtx
0x18000e862  test    edi, edi
0x18000e864  jz      short loc_18000E86E
0x18000e866  mov     ecx, ebx; dwErrCode
0x18000e868  call    cs:__imp_SetLastError
0x18000e86e  mov     rax, rsi
0x18000e871  jmp     loc_18000E7D5
0x18000f5ee  push    rbx
0x18000f5f0  push    rbp
0x18000f5f1  push    rdi
0x18000f5f2  sub     rsp, 30h
0x18000f5f6  mov     rbp, rdx
0x18000f5f9  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000f600  jz      short loc_18000F60B
0x18000f602  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000f609  jnz     short loc_18000F63E
0x18000f60b  cmp     qword ptr [rbp+38h], 0
0x18000f610  jnz     short loc_18000F621
0x18000f612  mov     edi, 1
0x18000f617  call    cs:__imp_GetLastError
0x18000f61d  mov     ebx, eax
0x18000f61f  jmp     short loc_18000F625
0x18000f621  xor     edi, edi
0x18000f623  xor     ebx, ebx
0x18000f625  mov     rdx, [rbp+30h]; ulCookie
0x18000f629  xor     ecx, ecx; dwFlags
0x18000f62b  call    cs:__imp_DeactivateActCtx
0x18000f631  test    edi, edi
0x18000f633  jz      short loc_18000F63E
0x18000f635  mov     ecx, ebx; dwErrCode
0x18000f637  call    cs:__imp_SetLastError
0x18000f63d  nop
0x18000f63e  add     rsp, 30h
0x18000f642  pop     rdi
0x18000f643  pop     rbp
0x18000f644  pop     rbx
0x18000f645  retn
```
