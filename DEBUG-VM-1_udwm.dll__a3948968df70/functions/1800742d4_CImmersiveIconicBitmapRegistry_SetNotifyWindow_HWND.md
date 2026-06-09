# CImmersiveIconicBitmapRegistry::SetNotifyWindow(HWND__ *)

- ea: `0x1800742d4`
- end: `0x180074377`
- name: `?SetNotifyWindow@CImmersiveIconicBitmapRegistry@@QEAAXPEAUHWND__@@@Z`
- size: `163`
- prototype: `void(CImmersiveIconicBitmapRegistry *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007c2b0`

## callees

- `0x180005948`
- `0x1800742d4`

## import_xrefs

- `USER32!GetDesktopID` at `0x1800742fb`
- `USER32!GetDesktopID` at `0x1800742fb`
- `USER32!GetWindowThreadProcessId` at `0x18007433d`
- `USER32!GetWindowThreadProcessId` at `0x18007434f`
- `USER32!GetWindowThreadProcessId` at `0x18007433d`
- `USER32!GetWindowThreadProcessId` at `0x18007434f`

## pseudocode

```c
void __fastcall CImmersiveIconicBitmapRegistry::SetNotifyWindow(CImmersiveIconicBitmapRegistry *this, HWND a2)
{
  HWND ShellWindowForDesktop; // rdi
  unsigned __int64 v5[3]; // [rsp+20h] [rbp-18h] BYREF
  DWORD dwProcessId; // [rsp+50h] [rbp+18h] BYREF
  DWORD v7; // [rsp+58h] [rbp+20h] BYREF

  v5[0] = 0;
  if ( (unsigned int)GetDesktopID(2, v5) )
  {
    ShellWindowForDesktop = CWindowList::GetShellWindowForDesktop(
                              *((CWindowList **)CDesktopManager::s_pDesktopManagerInstance + 53),
                              v5[0]);
    if ( ShellWindowForDesktop )
    {
      dwProcessId = 0;
      v7 = 0;
      if ( GetWindowThreadProcessId(a2, &dwProcessId) )
      {
        if ( GetWindowThreadProcessId(ShellWindowForDesktop, &v7) )
        {
          if ( v7 == dwProcessId )
            *((_QWORD *)this + 10) = a2;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800742d4  mov     rax, rsp
0x1800742d7  mov     [rax+8], rbx
0x1800742db  mov     [rax+10h], rsi
0x1800742df  push    rdi
0x1800742e0  sub     rsp, 30h
0x1800742e4  mov     rbx, rdx
0x1800742e7  mov     qword ptr [rax-18h], 0
0x1800742ef  mov     rsi, rcx
0x1800742f2  lea     rdx, [rax-18h]
0x1800742f6  mov     ecx, 2
0x1800742fb  call    cs:__imp_GetDesktopID
0x180074301  test    eax, eax
0x180074303  jz      short loc_180074367
0x180074305  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18007430c  mov     rdx, [rsp+38h+var_18]; unsigned __int64
0x180074311  mov     rcx, [rcx+1A8h]; this
0x180074318  call    ?GetShellWindowForDesktop@CWindowList@@QEAAPEAUHWND__@@_K@Z; CWindowList::GetShellWindowForDesktop(unsigned __int64)
0x18007431d  mov     rdi, rax
0x180074320  test    rax, rax
0x180074323  jz      short loc_180074367
0x180074325  lea     rdx, [rsp+38h+dwProcessId]; lpdwProcessId
0x18007432a  mov     [rsp+38h+dwProcessId], 0
0x180074332  mov     rcx, rbx; hWnd
0x180074335  mov     [rsp+38h+arg_18], 0
0x18007433d  call    cs:__imp_GetWindowThreadProcessId
0x180074343  test    eax, eax
0x180074345  jz      short loc_180074367
0x180074347  lea     rdx, [rsp+38h+arg_18]; lpdwProcessId
0x18007434c  mov     rcx, rdi; hWnd
0x18007434f  call    cs:__imp_GetWindowThreadProcessId
0x180074355  test    eax, eax
0x180074357  jz      short loc_180074367
0x180074359  mov     eax, [rsp+38h+dwProcessId]
0x18007435d  cmp     [rsp+38h+arg_18], eax
0x180074361  jnz     short loc_180074367
0x180074363  mov     [rsi+50h], rbx
0x180074367  mov     rbx, [rsp+38h+arg_0]
0x18007436c  mov     rsi, [rsp+38h+arg_8]
0x180074371  add     rsp, 30h
0x180074375  pop     rdi
0x180074376  retn
```
