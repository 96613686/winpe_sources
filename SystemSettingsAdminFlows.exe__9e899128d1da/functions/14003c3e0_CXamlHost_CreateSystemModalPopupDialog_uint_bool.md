# CXamlHost::CreateSystemModalPopupDialog(uint,bool)

- ea: `0x14003c3e0`
- end: `0x14003c447`
- name: `?CreateSystemModalPopupDialog@CXamlHost@@UEAAJI_N@Z`
- size: `103`
- prototype: `__int64 __fastcall(CXamlHost *__hidden this, unsigned int, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x14003c3e0`
- `0x14003d18c`
- `0x14003d630`
- `0x14003d904`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003c3f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003c3f1`
- `USER32!EnableMouseInPointer` at `0x14003c404`
- `USER32!EnableMouseInPointer` at `0x14003c404`
- `USER32!AllowSetForegroundWindow` at `0x14003c3f9`
- `USER32!AllowSetForegroundWindow` at `0x14003c3f9`

## pseudocode

```c
__int64 __fastcall CXamlHost::CreateSystemModalPopupDialog(CXamlHost *this, unsigned int a2, bool a3)
{
  DWORD CurrentProcessId; // eax
  int Error; // edi

  CurrentProcessId = GetCurrentProcessId();
  AllowSetForegroundWindow(CurrentProcessId);
  if ( ((unsigned int)EnableMouseInPointer(1) || (Error = ResultFromKnownLastError(), Error >= 0))
    && (Error = CXamlHost::InitSystemModalPopupDialogWindow(this, a2, a3), Error >= 0) )
  {
    *((_WORD *)this + 24) = 257;
  }
  else
  {
    CXamlHost::UninitPopupWindow(this);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x14003c3e0  push    rbx
0x14003c3e2  push    rbp
0x14003c3e3  push    rsi
0x14003c3e4  push    rdi
0x14003c3e5  sub     rsp, 28h
0x14003c3e9  mov     sil, r8b
0x14003c3ec  mov     ebp, edx
0x14003c3ee  mov     rbx, rcx
0x14003c3f1  call    cs:__imp_GetCurrentProcessId
0x14003c3f7  mov     ecx, eax; dwProcessId
0x14003c3f9  call    cs:__imp_AllowSetForegroundWindow
0x14003c3ff  mov     ecx, 1
0x14003c404  call    cs:__imp_EnableMouseInPointer
0x14003c40a  test    eax, eax
0x14003c40c  jnz     short loc_14003C419
0x14003c40e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14003c413  mov     edi, eax
0x14003c415  test    eax, eax
0x14003c417  js      short loc_14003C434
0x14003c419  mov     r8b, sil; bool
0x14003c41c  mov     edx, ebp; unsigned int
0x14003c41e  mov     rcx, rbx; this
0x14003c421  call    ?InitSystemModalPopupDialogWindow@CXamlHost@@IEAAJI_N@Z; CXamlHost::InitSystemModalPopupDialogWindow(uint,bool)
0x14003c426  mov     edi, eax
0x14003c428  test    eax, eax
0x14003c42a  js      short loc_14003C434
0x14003c42c  mov     word ptr [rbx+30h], 101h
0x14003c432  jmp     short loc_14003C43C
0x14003c434  mov     rcx, rbx; this
0x14003c437  call    ?UninitPopupWindow@CXamlHost@@IEAAXXZ; CXamlHost::UninitPopupWindow(void)
0x14003c43c  mov     eax, edi
0x14003c43e  add     rsp, 28h
0x14003c442  pop     rdi
0x14003c443  pop     rsi
0x14003c444  pop     rbp
0x14003c445  pop     rbx
0x14003c446  retn
```
