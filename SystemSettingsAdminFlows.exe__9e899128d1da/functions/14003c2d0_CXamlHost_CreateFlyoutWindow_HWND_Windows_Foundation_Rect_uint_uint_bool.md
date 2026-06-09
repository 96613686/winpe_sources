# CXamlHost::CreateFlyoutWindow(HWND__ *,Windows::Foundation::Rect,uint,uint,bool)

- ea: `0x14003c2d0`
- end: `0x14003c34d`
- name: `?CreateFlyoutWindow@CXamlHost@@UEAAJPEAUHWND__@@URect@Foundation@Windows@@II_N@Z`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x14003c2d0`
- `0x14003cea8`
- `0x14003d630`
- `0x14003d904`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003c2e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14003c2e7`
- `USER32!EnableMouseInPointer` at `0x14003c2fa`
- `USER32!EnableMouseInPointer` at `0x14003c2fa`
- `USER32!AllowSetForegroundWindow` at `0x14003c2ef`
- `USER32!AllowSetForegroundWindow` at `0x14003c2ef`

## pseudocode

```c
__int64 __fastcall CXamlHost::CreateFlyoutWindow(CXamlHost *a1, __int64 a2, _OWORD *a3, unsigned int a4)
{
  DWORD CurrentProcessId; // eax
  int Error; // ebx
  _OWORD v11[3]; // [rsp+30h] [rbp-38h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  AllowSetForegroundWindow(CurrentProcessId);
  if ( ((unsigned int)EnableMouseInPointer(1) || (Error = ResultFromKnownLastError(), Error >= 0))
    && (v11[0] = *a3, Error = CXamlHost::InitPopupFlyoutWindow(a1, a2, v11, a4), Error >= 0) )
  {
    *((_BYTE *)a1 + 48) = 1;
  }
  else
  {
    CXamlHost::UninitPopupWindow(a1);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x14003c2d0  push    rbx
0x14003c2d2  push    rbp
0x14003c2d3  push    rsi
0x14003c2d4  push    rdi
0x14003c2d5  push    r14
0x14003c2d7  sub     rsp, 40h
0x14003c2db  mov     esi, r9d
0x14003c2de  mov     rbp, r8
0x14003c2e1  mov     r14, rdx
0x14003c2e4  mov     rdi, rcx
0x14003c2e7  call    cs:__imp_GetCurrentProcessId
0x14003c2ed  mov     ecx, eax; dwProcessId
0x14003c2ef  call    cs:__imp_AllowSetForegroundWindow
0x14003c2f5  mov     ecx, 1
0x14003c2fa  call    cs:__imp_EnableMouseInPointer
0x14003c300  test    eax, eax
0x14003c302  jnz     short loc_14003C30F
0x14003c304  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14003c309  mov     ebx, eax
0x14003c30b  test    eax, eax
0x14003c30d  js      short loc_14003C338
0x14003c30f  movups  xmm0, xmmword ptr [rbp+0]
0x14003c313  mov     r9d, esi
0x14003c316  lea     r8, [rsp+68h+var_38]
0x14003c31b  mov     rdx, r14
0x14003c31e  mov     rcx, rdi
0x14003c321  movdqu  [rsp+68h+var_38], xmm0
0x14003c327  call    ?InitPopupFlyoutWindow@CXamlHost@@IEAAJPEAUHWND__@@URect@Foundation@Windows@@II_N@Z; CXamlHost::InitPopupFlyoutWindow(HWND__ *,Windows::Foundation::Rect,uint,uint,bool)
0x14003c32c  mov     ebx, eax
0x14003c32e  test    eax, eax
0x14003c330  js      short loc_14003C338
0x14003c332  mov     byte ptr [rdi+30h], 1
0x14003c336  jmp     short loc_14003C340
0x14003c338  mov     rcx, rdi; this
0x14003c33b  call    ?UninitPopupWindow@CXamlHost@@IEAAXXZ; CXamlHost::UninitPopupWindow(void)
0x14003c340  mov     eax, ebx
0x14003c342  add     rsp, 40h
0x14003c346  pop     r14
0x14003c348  pop     rdi
0x14003c349  pop     rsi
0x14003c34a  pop     rbp
0x14003c34b  pop     rbx
0x14003c34c  retn
```
