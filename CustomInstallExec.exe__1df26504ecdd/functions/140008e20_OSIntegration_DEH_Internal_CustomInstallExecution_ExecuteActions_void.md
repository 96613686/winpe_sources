# OSIntegration::DEH::Internal::CustomInstallExecution::ExecuteActions(void)

- ea: `0x140008e20`
- end: `0x140008ec0`
- name: `?ExecuteActions@CustomInstallExecution@Internal@DEH@OSIntegration@@IEAAKXZ`
- size: `160`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::CustomInstallExecution *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000a8a8`

## callees

- `0x140008bc4`
- `0x140008e20`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x140008e47`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x140008e9f`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x140008e47`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x140008e9f`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::ExecuteActions(
        OSIntegration::DEH::Internal::CustomInstallExecution *this)
{
  unsigned int v2; // esi
  unsigned __int64 i; // rdi
  OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *v4; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ecx

  v2 = 0;
  PostMessageW(g_mainWindow, 0x402u, *((_QWORD *)this + 8), 0);
  for ( i = 0; i < *((_QWORD *)this + 8); ++i )
  {
    if ( g_earlyExit )
      break;
    if ( i < *((_QWORD *)this + 8) )
      v4 = *(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper **)(*((_QWORD *)this + 6) + 8 * i);
    else
      v4 = 0;
    if ( *((_DWORD *)v4 + 19) != 1 )
    {
      v5 = OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction(
             v4,
             *((const unsigned __int16 **)this + 4),
             *((const unsigned __int16 **)this + 1));
      v6 = v2 + 1;
      if ( !v5 )
        v6 = v2;
      v2 = v6;
    }
    PostMessageW(g_mainWindow, 0x403u, 0, 0);
  }
  return v2;
}

```

## disassembly

```asm
0x140008e20  mov     [rsp+arg_0], rbx
0x140008e25  mov     [rsp+arg_8], rsi
0x140008e2a  push    rdi
0x140008e2b  sub     rsp, 20h
0x140008e2f  mov     r8, [rcx+40h]; wParam
0x140008e33  mov     rbx, rcx
0x140008e36  mov     rcx, cs:?g_mainWindow@@3PEAUHWND__@@EA; hWnd
0x140008e3d  xor     r9d, r9d; lParam
0x140008e40  mov     edx, 402h; Msg
0x140008e45  xor     esi, esi
0x140008e47  call    cs:__imp_PostMessageW
0x140008e4d  xor     edi, edi
0x140008e4f  cmp     [rbx+40h], rsi
0x140008e53  jbe     short loc_140008EAE
0x140008e55  cmp     cs:?g_earlyExit@@3_NA, 0; bool g_earlyExit
0x140008e5c  jnz     short loc_140008EAE
0x140008e5e  cmp     rdi, [rbx+40h]
0x140008e62  jb      short loc_140008E68
0x140008e64  xor     ecx, ecx
0x140008e66  jmp     short loc_140008E70
0x140008e68  mov     rax, [rbx+30h]
0x140008e6c  mov     rcx, [rax+rdi*8]; this
0x140008e70  cmp     dword ptr [rcx+4Ch], 1
0x140008e74  jz      short loc_140008E8D
0x140008e76  mov     r8, [rbx+8]; unsigned __int16 *
0x140008e7a  mov     rdx, [rbx+20h]; unsigned __int16 *
0x140008e7e  call    ?ExecuteAction@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAKPEBG0@Z; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::ExecuteAction(ushort const *,ushort const *)
0x140008e83  lea     ecx, [rsi+1]
0x140008e86  test    eax, eax
0x140008e88  cmovz   ecx, esi
0x140008e8b  mov     esi, ecx
0x140008e8d  mov     rcx, cs:?g_mainWindow@@3PEAUHWND__@@EA; hWnd
0x140008e94  xor     r9d, r9d; lParam
0x140008e97  xor     r8d, r8d; wParam
0x140008e9a  mov     edx, 403h; Msg
0x140008e9f  call    cs:__imp_PostMessageW
0x140008ea5  inc     rdi
0x140008ea8  cmp     rdi, [rbx+40h]
0x140008eac  jb      short loc_140008E55
0x140008eae  mov     rbx, [rsp+28h+arg_0]
0x140008eb3  mov     eax, esi
0x140008eb5  mov     rsi, [rsp+28h+arg_8]
0x140008eba  add     rsp, 20h
0x140008ebe  pop     rdi
0x140008ebf  retn
```
