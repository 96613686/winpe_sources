# LogAdapter::WdsLogger::InternalWriteLog(LogAdapter::LogLevel,char const *)

- ea: `0x1400069e0`
- end: `0x140006b2d`
- name: `?InternalWriteLog@WdsLogger@LogAdapter@@UEAAJW4LogLevel@2@PEBD@Z`
- size: `333`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x140002310`
- `0x14000692c`
- `0x1400069e0`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140006a2d`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x140006a2d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140006a4a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x140006a4a`

## string_xrefs

- `0x140006a24`: `wdscore.dll`

## pseudocode

```c
__int64 __fastcall LogAdapter::WdsLogger::InternalWriteLog(__int64 a1, int a2, __int64 a3)
{
  HMODULE *v6; // rsi
  HMODULE *InitPointer; // rax
  HMODULE v8; // rcx
  void (__fastcall *v9)(_QWORD *, __int64, const char *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD); // r10
  int v10; // ebx
  __int64 v11; // rdx
  _QWORD v13[2]; // [rsp+60h] [rbp-48h] BYREF
  __int128 v14; // [rsp+70h] [rbp-38h]

  if ( !*(_BYTE *)(a1 + 4224) )
  {
    v6 = (HMODULE *)(a1 + 4208);
    InitPointer = (HMODULE *)Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::GetInitPointer(a1 + 4208);
    if ( GetModuleHandleExW(0, L"wdscore.dll", InitPointer) )
      v8 = *v6;
    else
      v8 = (HMODULE)0x140000000LL;
    *(_QWORD *)(a1 + 4216) = GetProcAddress(v8, "WdsSetupLogMessageA");
    *(_BYTE *)(a1 + 4224) = 1;
  }
  v9 = *(void (__fastcall **)(_QWORD *, __int64, const char *, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))(a1 + 4216);
  if ( v9 )
  {
    v13[0] = 0x4000000;
    v14 = 0;
    if ( a2 )
    {
      v10 = a2 - 2;
      if ( v10 )
      {
        if ( v10 == 1 )
          LODWORD(v13[0]) = 0x2000000;
      }
      else
      {
        LODWORD(v13[0]) = 50331648;
      }
    }
    else
    {
      LODWORD(v13[0]) = 1728053248;
    }
    v11 = *(unsigned int *)(a1 + 4228);
    v13[1] = a3;
    v9(v13, v11, "D", 0, 0, 0, 0, 0, 0, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1400069e0  mov     [rsp+arg_8], rbx
0x1400069e5  push    rbp
0x1400069e6  push    rsi
0x1400069e7  push    rdi
0x1400069e8  sub     rsp, 90h
0x1400069ef  mov     rax, cs:__security_cookie
0x1400069f6  xor     rax, rsp
0x1400069f9  mov     [rsp+0A8h+var_28], rax
0x140006a01  cmp     byte ptr [rcx+1080h], 0
0x140006a08  mov     rbp, r8
0x140006a0b  mov     ebx, edx
0x140006a0d  mov     rdi, rcx
0x140006a10  jnz     short loc_140006A5E
0x140006a12  lea     rsi, [rcx+1070h]
0x140006a19  mov     rcx, rsi
0x140006a1c  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAPEAPEAUHINSTANCE__@@XZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::GetInitPointer(void)
0x140006a21  mov     r8, rax; phModule
0x140006a24  lea     rdx, aWdscoreDll; "wdscore.dll"
0x140006a2b  xor     ecx, ecx; dwFlags
0x140006a2d  call    cs:__imp_GetModuleHandleExW
0x140006a33  test    eax, eax
0x140006a35  jz      short loc_140006A3C
0x140006a37  mov     rcx, [rsi]
0x140006a3a  jmp     short loc_140006A43
0x140006a3c  lea     rcx, cs:140000000h; hModule
0x140006a43  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x140006a4a  call    cs:__imp_GetProcAddress
0x140006a50  mov     [rdi+1078h], rax
0x140006a57  mov     byte ptr [rdi+1080h], 1
0x140006a5e  mov     r10, [rdi+1078h]
0x140006a65  test    r10, r10
0x140006a68  jz      loc_140006B08
0x140006a6e  mov     [rsp+0A8h+var_48], 4000000h
0x140006a77  xorps   xmm0, xmm0
0x140006a7a  movdqu  [rsp+0A8h+var_38], xmm0
0x140006a80  test    ebx, ebx
0x140006a82  jz      short loc_140006AA2
0x140006a84  sub     ebx, 2
0x140006a87  jz      short loc_140006A98
0x140006a89  cmp     ebx, 1
0x140006a8c  jnz     short loc_140006AAA
0x140006a8e  mov     dword ptr [rsp+0A8h+var_48], 2000000h
0x140006a96  jmp     short loc_140006AAA
0x140006a98  mov     dword ptr [rsp+0A8h+var_48], 3000000h
0x140006aa0  jmp     short loc_140006AAA
0x140006aa2  mov     dword ptr [rsp+0A8h+var_48], 67000000h
0x140006aaa  mov     edx, [rdi+1084h]
0x140006ab0  lea     r8, aD_0; "D"
0x140006ab7  mov     [rsp+0A8h+var_58], 0
0x140006abf  lea     rcx, [rsp+0A8h+var_48]
0x140006ac4  mov     [rsp+0A8h+var_60], 0
0x140006acd  xor     r9d, r9d
0x140006ad0  mov     [rsp+0A8h+var_68], 0
0x140006ad8  mov     rax, r10
0x140006adb  mov     [rsp+0A8h+var_70], 0
0x140006ae4  mov     [rsp+0A8h+var_78], 0
0x140006aed  mov     [rsp+0A8h+var_80], 0
0x140006af6  mov     [rsp+0A8h+var_88], 0
0x140006afe  mov     [rsp+0A8h+var_40], rbp
0x140006b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b08  xor     eax, eax
0x140006b0a  mov     rcx, [rsp+0A8h+var_28]
0x140006b12  xor     rcx, rsp; StackCookie
0x140006b15  call    __security_check_cookie
0x140006b1a  mov     rbx, [rsp+0A8h+arg_8]
0x140006b22  add     rsp, 90h
0x140006b29  pop     rdi
0x140006b2a  pop     rsi
0x140006b2b  pop     rbp
0x140006b2c  retn
```
