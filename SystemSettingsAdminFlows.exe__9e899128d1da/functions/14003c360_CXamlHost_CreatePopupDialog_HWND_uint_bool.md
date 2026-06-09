# CXamlHost::CreatePopupDialog(HWND__ *,uint,bool)

- ea: `0x14003c360`
- end: `0x14003c3d3`
- name: `?CreatePopupDialog@CXamlHost@@UEAAJPEAUHWND__@@I_N@Z`
- size: `115`
- prototype: `__int64 __fastcall(CXamlHost *__hidden this, HWND, unsigned int, bool)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x14003c360`
- `0x14003cc58`
- `0x14003d630`
- `0x14003d904`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003c377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003c377`
- `USER32!EnableMouseInPointer` at `0x14003c38a`
- `USER32!EnableMouseInPointer` at `0x14003c38a`
- `USER32!AllowSetForegroundWindow` at `0x14003c37f`
- `USER32!AllowSetForegroundWindow` at `0x14003c37f`

## pseudocode

```c
__int64 __fastcall CXamlHost::CreatePopupDialog(CXamlHost *this, HWND a2, unsigned int a3, bool a4)
{
  DWORD CurrentProcessId; // eax
  int Error; // edi

  CurrentProcessId = GetCurrentProcessId();
  AllowSetForegroundWindow(CurrentProcessId);
  if ( ((unsigned int)EnableMouseInPointer(1) || (Error = ResultFromKnownLastError(), Error >= 0))
    && (Error = CXamlHost::InitPopupDialogWindow(this, a2, a3, a4), Error >= 0) )
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
0x14003c360  push    rbx
0x14003c362  push    rbp
0x14003c363  push    rsi
0x14003c364  push    rdi
0x14003c365  push    r14
0x14003c367  sub     rsp, 20h
0x14003c36b  mov     sil, r9b
0x14003c36e  mov     ebp, r8d
0x14003c371  mov     r14, rdx
0x14003c374  mov     rbx, rcx
0x14003c377  call    cs:__imp_GetCurrentProcessId
0x14003c37d  mov     ecx, eax; dwProcessId
0x14003c37f  call    cs:__imp_AllowSetForegroundWindow
0x14003c385  mov     ecx, 1
0x14003c38a  call    cs:__imp_EnableMouseInPointer
0x14003c390  test    eax, eax
0x14003c392  jnz     short loc_14003C39F
0x14003c394  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14003c399  mov     edi, eax
0x14003c39b  test    eax, eax
0x14003c39d  js      short loc_14003C3BE
0x14003c39f  mov     r9b, sil; bool
0x14003c3a2  mov     r8d, ebp; unsigned int
0x14003c3a5  mov     rdx, r14; HWND
0x14003c3a8  mov     rcx, rbx; this
0x14003c3ab  call    ?InitPopupDialogWindow@CXamlHost@@IEAAJPEAUHWND__@@I_N@Z; CXamlHost::InitPopupDialogWindow(HWND__ *,uint,bool)
0x14003c3b0  mov     edi, eax
0x14003c3b2  test    eax, eax
0x14003c3b4  js      short loc_14003C3BE
0x14003c3b6  mov     word ptr [rbx+30h], 101h
0x14003c3bc  jmp     short loc_14003C3C6
0x14003c3be  mov     rcx, rbx; this
0x14003c3c1  call    ?UninitPopupWindow@CXamlHost@@IEAAXXZ; CXamlHost::UninitPopupWindow(void)
0x14003c3c6  mov     eax, edi
0x14003c3c8  add     rsp, 20h
0x14003c3cc  pop     r14
0x14003c3ce  pop     rdi
0x14003c3cf  pop     rsi
0x14003c3d0  pop     rbp
0x14003c3d1  pop     rbx
0x14003c3d2  retn
```
