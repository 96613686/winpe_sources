# LogAdapter::WdsLogger::InternalWriteLog(LogAdapter::LogLevel,char const *)

- ea: `0x140007770`
- end: `0x1400078bd`
- name: `?InternalWriteLog@WdsLogger@LogAdapter@@UEAAJW4LogLevel@2@PEBD@Z`
- size: `333`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400023e0`
- `0x140007630`
- `0x140007770`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400077da`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1400077da`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1400077bd`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleExW` at `0x1400077bd`

## string_xrefs

- `0x1400077b4`: `wdscore.dll`

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
    InitPointer = (HMODULE *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(a1 + 4208);
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
0x140007770  mov     [rsp+arg_8], rbx
0x140007775  push    rbp
0x140007776  push    rsi
0x140007777  push    rdi
0x140007778  sub     rsp, 90h
0x14000777f  mov     rax, cs:__security_cookie
0x140007786  xor     rax, rsp
0x140007789  mov     [rsp+0A8h+var_28], rax
0x140007791  cmp     byte ptr [rcx+1080h], 0
0x140007798  mov     rbp, r8
0x14000779b  mov     ebx, edx
0x14000779d  mov     rdi, rcx
0x1400077a0  jnz     short loc_1400077EE
0x1400077a2  lea     rsi, [rcx+1070h]
0x1400077a9  mov     rcx, rsi
0x1400077ac  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x1400077b1  mov     r8, rax; phModule
0x1400077b4  lea     rdx, aWdscoreDll; "wdscore.dll"
0x1400077bb  xor     ecx, ecx; dwFlags
0x1400077bd  call    cs:__imp_GetModuleHandleExW
0x1400077c3  test    eax, eax
0x1400077c5  jz      short loc_1400077CC
0x1400077c7  mov     rcx, [rsi]
0x1400077ca  jmp     short loc_1400077D3
0x1400077cc  lea     rcx, cs:140000000h; hModule
0x1400077d3  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x1400077da  call    cs:__imp_GetProcAddress
0x1400077e0  mov     [rdi+1078h], rax
0x1400077e7  mov     byte ptr [rdi+1080h], 1
0x1400077ee  mov     r10, [rdi+1078h]
0x1400077f5  test    r10, r10
0x1400077f8  jz      loc_140007898
0x1400077fe  mov     [rsp+0A8h+var_48], 4000000h
0x140007807  xorps   xmm0, xmm0
0x14000780a  movdqu  [rsp+0A8h+var_38], xmm0
0x140007810  test    ebx, ebx
0x140007812  jz      short loc_140007832
0x140007814  sub     ebx, 2
0x140007817  jz      short loc_140007828
0x140007819  cmp     ebx, 1
0x14000781c  jnz     short loc_14000783A
0x14000781e  mov     dword ptr [rsp+0A8h+var_48], 2000000h
0x140007826  jmp     short loc_14000783A
0x140007828  mov     dword ptr [rsp+0A8h+var_48], 3000000h
0x140007830  jmp     short loc_14000783A
0x140007832  mov     dword ptr [rsp+0A8h+var_48], 67000000h
0x14000783a  mov     edx, [rdi+1084h]
0x140007840  lea     r8, aD_0; "D"
0x140007847  mov     [rsp+0A8h+var_58], 0
0x14000784f  lea     rcx, [rsp+0A8h+var_48]
0x140007854  mov     [rsp+0A8h+var_60], 0
0x14000785d  xor     r9d, r9d
0x140007860  mov     [rsp+0A8h+var_68], 0
0x140007868  mov     rax, r10
0x14000786b  mov     [rsp+0A8h+var_70], 0
0x140007874  mov     [rsp+0A8h+var_78], 0
0x14000787d  mov     [rsp+0A8h+var_80], 0
0x140007886  mov     [rsp+0A8h+var_88], 0
0x14000788e  mov     [rsp+0A8h+var_40], rbp
0x140007893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007898  xor     eax, eax
0x14000789a  mov     rcx, [rsp+0A8h+var_28]
0x1400078a2  xor     rcx, rsp; StackCookie
0x1400078a5  call    __security_check_cookie
0x1400078aa  mov     rbx, [rsp+0A8h+arg_8]
0x1400078b2  add     rsp, 90h
0x1400078b9  pop     rdi
0x1400078ba  pop     rsi
0x1400078bb  pop     rbp
0x1400078bc  retn
```
