# IsolationAwareImageList_ReplaceIcon

- ea: `0x18000e948`
- end: `0x18000ea1a`
- name: `IsolationAwareImageList_ReplaceIcon`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000dc60`

## callees

- `0x18000e604`
- `0x18000e948`
- `0x18000eaf0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f6f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea0d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f6f3`
- `KERNEL32!DeactivateActCtx` at `0x18000ea01`
- `KERNEL32!DeactivateActCtx` at `0x18000f6e7`
- `KERNEL32!DeactivateActCtx` at `0x18000ea01`
- `KERNEL32!DeactivateActCtx` at `0x18000f6e7`

## string_xrefs

- `0x18000e9a0`: `ImageList_ReplaceIcon`

## pseudocode

```c
__int64 __fastcall IsolationAwareImageList_ReplaceIcon(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  __int64 (__fastcall *v6)(__int64, __int64, __int64); // rbx
  __int64 v8; // rax
  int v9; // esi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+78h] [rbp+20h] BYREF

  v5 = -1;
  v6 = (__int64 (__fastcall *)(__int64, __int64, __int64))`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0xFFFFFFFFLL;
  }
  if ( !v6 )
  {
    v8 = CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY("ImageList_ReplaceIcon");
    v6 = (__int64 (__fastcall *)(__int64, __int64, __int64))v8;
    if ( !v8 )
      goto LABEL_9;
    `IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn = v8;
  }
  v5 = v6(a1, 0xFFFFFFFFLL, a3);
LABEL_9:
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( v5 == -1 )
    {
      v9 = 1;
      LastError = GetLastError();
    }
    else
    {
      v9 = 0;
      LastError = 0;
    }
    DeactivateActCtx(0, ulCookie);
    if ( v9 )
      SetLastError(LastError);
  }
  return v5;
}

```

## disassembly

```asm
0x18000e948  push    rbx
0x18000e94a  push    rsi
0x18000e94b  push    rdi
0x18000e94c  push    r14
0x18000e94e  sub     rsp, 38h
0x18000e952  mov     rsi, r8
0x18000e955  mov     r14, rcx
0x18000e958  or      edi, 0FFFFFFFFh
0x18000e95b  mov     [rsp+58h+var_38], edi
0x18000e95f  mov     rbx, cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x18000e966  mov     [rsp+58h+ulCookie], 0
0x18000e96f  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e976  jnz     short loc_18000E99B
0x18000e978  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e97f  jnz     short loc_18000E99B
0x18000e981  lea     rcx, [rsp+58h+ulCookie]; lpCookie
0x18000e986  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18000e98b  test    eax, eax
0x18000e98d  jnz     short loc_18000E99B
0x18000e98f  or      eax, edi
0x18000e991  add     rsp, 38h
0x18000e995  pop     r14
0x18000e997  pop     rdi
0x18000e998  pop     rsi
0x18000e999  pop     rbx
0x18000e99a  retn
0x18000e99b  test    rbx, rbx
0x18000e99e  jnz     short loc_18000E9BB
0x18000e9a0  lea     rcx, aImagelistRepla; "ImageList_ReplaceIcon"
0x18000e9a7  call    CommctrlIsolationAwarePrivatetRgCebPnQQeRff_pbZPgYQP_QYY
0x18000e9ac  mov     rbx, rax
0x18000e9af  test    rax, rax
0x18000e9b2  jz      short loc_18000E9D2
0x18000e9b4  mov     cs:?s_pfn@?1??IsolationAwareImageList_ReplaceIcon@@9@4P6AHPEAU_IMAGELIST@@HPEAUHICON__@@@ZEA, rax; int (*`IsolationAwareImageList_ReplaceIcon'::`2'::s_pfn)(_IMAGELIST *,int,HICON__ *)
0x18000e9bb  mov     r8, rsi
0x18000e9be  or      edx, 0FFFFFFFFh
0x18000e9c1  mov     rcx, r14
0x18000e9c4  mov     rax, rbx
0x18000e9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9cc  mov     edi, eax
0x18000e9ce  mov     [rsp+58h+var_38], eax
0x18000e9d2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000e9d9  jz      short loc_18000E9E4
0x18000e9db  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000e9e2  jnz     short loc_18000EA13
0x18000e9e4  cmp     edi, 0FFFFFFFFh
0x18000e9e7  jnz     short loc_18000E9F6
0x18000e9e9  lea     esi, [rdi+2]
0x18000e9ec  call    cs:__imp_GetLastError
0x18000e9f2  mov     ebx, eax
0x18000e9f4  jmp     short loc_18000E9FA
0x18000e9f6  xor     esi, esi
0x18000e9f8  xor     ebx, ebx
0x18000e9fa  mov     rdx, [rsp+58h+ulCookie]; ulCookie
0x18000e9ff  xor     ecx, ecx; dwFlags
0x18000ea01  call    cs:__imp_DeactivateActCtx
0x18000ea07  test    esi, esi
0x18000ea09  jz      short loc_18000EA13
0x18000ea0b  mov     ecx, ebx; dwErrCode
0x18000ea0d  call    cs:__imp_SetLastError
0x18000ea13  mov     eax, edi
0x18000ea15  jmp     loc_18000E991
0x18000f6ab  push    rbx
0x18000f6ad  push    rbp
0x18000f6ae  push    rdi
0x18000f6af  sub     rsp, 20h
0x18000f6b3  mov     rbp, rdx
0x18000f6b6  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18000f6bd  jz      short loc_18000F6C8
0x18000f6bf  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000f6c6  jnz     short loc_18000F6FA
0x18000f6c8  cmp     dword ptr [rbp+20h], 0FFFFFFFFh
0x18000f6cc  jnz     short loc_18000F6DD
0x18000f6ce  mov     edi, 1
0x18000f6d3  call    cs:__imp_GetLastError
0x18000f6d9  mov     ebx, eax
0x18000f6db  jmp     short loc_18000F6E1
0x18000f6dd  xor     edi, edi
0x18000f6df  xor     ebx, ebx
0x18000f6e1  mov     rdx, [rbp+78h]; ulCookie
0x18000f6e5  xor     ecx, ecx; dwFlags
0x18000f6e7  call    cs:__imp_DeactivateActCtx
0x18000f6ed  test    edi, edi
0x18000f6ef  jz      short loc_18000F6FA
0x18000f6f1  mov     ecx, ebx; dwErrCode
0x18000f6f3  call    cs:__imp_SetLastError
0x18000f6f9  nop
0x18000f6fa  add     rsp, 20h
0x18000f6fe  pop     rdi
0x18000f6ff  pop     rbp
0x18000f700  pop     rbx
0x18000f701  retn
```
