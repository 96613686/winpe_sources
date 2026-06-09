# DedupUtil::ScopedPrivileges::RestorePrivileges(void)

- ea: `0x140067dd4`
- end: `0x140067e6a`
- name: `?RestorePrivileges@ScopedPrivileges@DedupUtil@@QEAAKXZ`
- size: `150`
- prototype: `unsigned int __fastcall(DedupUtil::ScopedPrivileges *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140064c9c`
- `0x140065e44`

## callees

- `0x1400635dc`
- `0x140067dd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067e1f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140067e0f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x140067e0f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140067e51`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140067e51`

## string_xrefs

- `0x140067e35`: `Failed to restore original security privielges, error = 0x%x\n`

## pseudocode

```c
__int64 __fastcall DedupUtil::ScopedPrivileges::RestorePrivileges(DedupUtil::ScopedPrivileges *this)
{
  char *v2; // rcx
  struct _TOKEN_PRIVILEGES *v3; // r8
  DWORD LastError; // [rsp+40h] [rbp+8h] BYREF

  v2 = *(char **)this;
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v3 = (struct _TOKEN_PRIVILEGES *)*((_QWORD *)this + 1);
    if ( v3 )
    {
      if ( !AdjustTokenPrivileges(v2, 0, v3, *((_DWORD *)this + 4) + 16, 0, 0) )
      {
        LastError = GetLastError();
        DedupUtil::Print<unsigned long &>(
          6,
          L"Failed to restore original security privielges, error = 0x%x\n",
          &LastError);
        return LastError;
      }
      if ( *((_BYTE *)this + 20) )
      {
        RevertToSelf();
        *((_BYTE *)this + 20) = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140067dd4  push    rbx
0x140067dd6  sub     rsp, 30h
0x140067dda  mov     rbx, rcx
0x140067ddd  mov     rcx, [rcx]; TokenHandle
0x140067de0  lea     rax, [rcx-1]
0x140067de4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140067de8  ja      short loc_140067E61
0x140067dea  mov     r8, [rbx+8]; NewState
0x140067dee  test    r8, r8
0x140067df1  jz      short loc_140067E61
0x140067df3  mov     r9d, [rbx+10h]
0x140067df7  xor     edx, edx; DisableAllPrivileges
0x140067df9  add     r9d, 10h; BufferLength
0x140067dfd  mov     [rsp+38h+ReturnLength], 0; ReturnLength
0x140067e06  mov     [rsp+38h+PreviousState], 0; PreviousState
0x140067e0f  call    cs:__imp_AdjustTokenPrivileges
0x140067e16  nop     dword ptr [rax+rax+00h]
0x140067e1b  test    eax, eax
0x140067e1d  jnz     short loc_140067E4B
0x140067e1f  call    cs:__imp_GetLastError
0x140067e26  nop     dword ptr [rax+rax+00h]
0x140067e2b  lea     r8, [rsp+38h+arg_0]
0x140067e30  mov     ecx, 6
0x140067e35  lea     rdx, aFailedToRestor; "Failed to restore original security pri"...
0x140067e3c  mov     [rsp+38h+arg_0], eax
0x140067e40  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x140067e45  mov     eax, [rsp+38h+arg_0]
0x140067e49  jmp     short loc_140067E63
0x140067e4b  cmp     byte ptr [rbx+14h], 0
0x140067e4f  jz      short loc_140067E61
0x140067e51  call    cs:__imp_RevertToSelf
0x140067e58  nop     dword ptr [rax+rax+00h]
0x140067e5d  mov     byte ptr [rbx+14h], 0
0x140067e61  xor     eax, eax
0x140067e63  add     rsp, 30h
0x140067e67  pop     rbx
0x140067e68  retn
```
