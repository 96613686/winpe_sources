# PrintCore::ImpersonateUserRAII::ImpersonateUserRAII(void *)

- ea: `0x180022b04`
- end: `0x180022b52`
- name: `??0ImpersonateUserRAII@PrintCore@@QEAA@PEAX@Z`
- size: `78`
- prototype: `PrintCore::ImpersonateUserRAII *__fastcall(PrintCore::ImpersonateUserRAII *this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180022c58`
- `0x1800256ac`

## callees

- `0x18001dae4`
- `0x180022b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b19`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022b0f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022b0f`

## pseudocode

```c
PrintCore::ImpersonateUserRAII *__fastcall PrintCore::ImpersonateUserRAII::ImpersonateUserRAII(
        PrintCore::ImpersonateUserRAII *this,
        void *a2)
{
  signed int LastError; // eax
  bool v4; // sf
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !SetThreadToken(0, a2) )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v4 = LastError < 0;
    }
    if ( v4 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C1,
        (unsigned int)"onecoreuap\\internal\\printscan\\inc\\private\\print\\platform\\RAIIObjects.h",
        (const char *)(unsigned int)LastError,
        v6);
  }
  return this;
}

```

## disassembly

```asm
0x180022b04  push    rbx; int
0x180022b06  sub     rsp, 20h
0x180022b0a  mov     rbx, rcx
0x180022b0d  xor     ecx, ecx; Thread
0x180022b0f  call    cs:__imp_SetThreadToken
0x180022b15  test    eax, eax
0x180022b17  jnz     short loc_180022B49
0x180022b19  call    cs:__imp_GetLastError
0x180022b1f  test    eax, eax
0x180022b21  jle     short loc_180022B2D
0x180022b23  movzx   eax, ax
0x180022b26  or      eax, 80070000h
0x180022b2b  test    eax, eax
0x180022b2d  jns     short loc_180022B49
0x180022b2f  mov     rcx, [rsp+28h]; this
0x180022b34  lea     r8, aOnecoreuapInte_5; "onecoreuap\\internal\\printscan\\inc\\p"...
0x180022b3b  mov     r9d, eax; char *
0x180022b3e  mov     edx, 1C1h; void *
0x180022b43  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180022b49  mov     rax, rbx
0x180022b4c  add     rsp, 20h
0x180022b50  pop     rbx
0x180022b51  retn
```
