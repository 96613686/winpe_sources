# DidAppSurviveOSUpgradeForUser

- ea: `0x1800069e0`
- end: `0x180006beb`
- name: `DidAppSurviveOSUpgradeForUser`
- size: `523`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004920`
- `0x1800069e0`
- `0x180006c00`
- `0x180006d40`
- `0x180007860`
- `0x180007a10`
- `0x180017f50`
- `0x180018248`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006aed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006aed`

## string_xrefs

- `0x180006b1b`: `onecore\base\appmodel\common\stringbuilder.cpp`
- `0x180006a1d`: `DownlevelInstalled`

## pseudocode

```c
__int64 __fastcall DidAppSurviveOSUpgradeForUser(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        _BYTE *a3,
        struct Common::StringBuffer *a4)
{
  const unsigned __int16 *v5; // r14
  int AllUserChildStorePath; // ebx
  int appended; // eax
  int v9; // eax
  LSTATUS v10; // eax
  __int64 v11; // rdx
  int phkResult; // [rsp+20h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+30h] [rbp-30h] BYREF
  int v15; // [rsp+40h] [rbp-20h]
  const int *v16; // [rsp+48h] [rbp-18h] BYREF
  LPCWSTR *v17; // [rsp+50h] [rbp-10h]
  LPCWSTR *v18; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HKEY v20; // [rsp+80h] [rbp+20h] BYREF

  v5 = a2;
  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  *a3 = 0;
  v15 = 0;
  LOBYTE(a2) = 1;
  *(_OWORD *)lpSubKey = 0;
  AllUserChildStorePath = AppxAllUserStore::GetAllUserChildStorePath(
                            (AppxAllUserStore *)L"DownlevelInstalled",
                            a2,
                            (unsigned int *)lpSubKey,
                            a4);
  if ( AllUserChildStorePath < 0 )
  {
    v11 = 1168;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\exports.cpp",
      (const char *)(unsigned int)AllUserChildStorePath,
      phkResult);
    if ( lpSubKey[1] )
      Common::GlobalHeap::Free((void *)lpSubKey[1]);
    return (unsigned int)AllUserChildStorePath;
  }
  v17 = lpSubKey;
  v16 = &Common::StringBufferBuilder::`vftable';
  v18 = lpSubKey;
  appended = Common::StringBuilder::AppendString((Common::StringBuilder *)&v16, a1);
  AllUserChildStorePath = appended;
  if ( appended < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x494,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\exports.cpp",
      (const char *)(unsigned int)appended,
      phkResult);
    Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpSubKey);
    return (unsigned int)AllUserChildStorePath;
  }
  if ( *(_DWORD *)v17 == 0x3FFFFFFF )
  {
    AllUserChildStorePath = -2147023613;
    goto LABEL_14;
  }
  v9 = (*(__int64 (__fastcall **)(const int **, _QWORD))v16)(&v16, (unsigned int)(*(_DWORD *)v17 + 1));
  AllUserChildStorePath = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1B,
      (int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
      (const char *)(unsigned int)v9);
LABEL_14:
    v11 = 1175;
    goto LABEL_15;
  }
  v17[1][*(_DWORD *)v17 - 1] = 92;
  AllUserChildStorePath = Common::StringBuilder::AppendString((Common::StringBuilder *)&v16, v5);
  if ( AllUserChildStorePath < 0 )
  {
    v11 = 1176;
    goto LABEL_15;
  }
  v20 = 0;
  v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[1], 0, 0x20019u, &v20);
  AllUserChildStorePath = v10;
  if ( !v10 )
  {
    *a3 = 1;
    goto LABEL_12;
  }
  if ( (unsigned int)(v10 - 2) > 1 )
  {
    if ( v10 > 0 )
      AllUserChildStorePath = (unsigned __int16)v10 | 0x80070000;
    Common::AutoHandleCloseHKEY<HKEY__ *>(v20);
    if ( AllUserChildStorePath >= 0 )
      goto LABEL_19;
    v11 = 1179;
    goto LABEL_15;
  }
  *a3 = 0;
LABEL_12:
  Common::AutoHandleCloseHKEY<HKEY__ *>(v20);
LABEL_19:
  if ( lpSubKey[1] )
    Common::GlobalHeap::Free((void *)lpSubKey[1]);
  return 0;
}

```

## disassembly

```asm
0x1800069e0  mov     [rsp-18h+arg_8], rbx
0x1800069e5  mov     [rsp-18h+arg_10], rsi
0x1800069ea  push    rbp
0x1800069eb  push    rdi
0x1800069ec  push    r14
0x1800069ee  mov     rbp, rsp
0x1800069f1  sub     rsp, 60h
0x1800069f5  mov     rdi, r8
0x1800069f8  mov     r14, rdx
0x1800069fb  mov     rsi, rcx
0x1800069fe  test    rcx, rcx
0x180006a01  jz      loc_180006BAF
0x180006a07  test    rdx, rdx
0x180006a0a  jz      loc_180006BAF
0x180006a10  test    r8, r8
0x180006a13  jz      loc_180006BAF
0x180006a19  mov     byte ptr [r8], 0
0x180006a1d  lea     rcx, ?downlevelInstalledApplicationsString@AppxAllUserStore@@3QBGB; "DownlevelInstalled"
0x180006a24  xor     eax, eax
0x180006a26  lea     r8, [rbp+lpSubKey]; bool
0x180006a2a  xorps   xmm0, xmm0
0x180006a2d  mov     [rbp+var_20], eax
0x180006a30  mov     dl, 1; unsigned __int16 *
0x180006a32  movups  xmmword ptr [rbp+lpSubKey], xmm0
0x180006a36  call    ?GetAllUserChildStorePath@AppxAllUserStore@@YAJPEBG_NPEAVStringBuffer@Common@@@Z; AppxAllUserStore::GetAllUserChildStorePath(ushort const *,bool,Common::StringBuffer *)
0x180006a3b  mov     ebx, eax
0x180006a3d  test    eax, eax
0x180006a3f  js      loc_180006B9A
0x180006a45  lea     rax, [rbp+lpSubKey]
0x180006a49  mov     rdx, rsi; unsigned __int16 *
0x180006a4c  mov     [rbp+var_10], rax
0x180006a50  lea     rcx, [rbp+var_18]; this
0x180006a54  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180006a5b  mov     [rbp+var_18], rax
0x180006a5f  lea     rax, [rbp+lpSubKey]
0x180006a63  mov     [rbp+var_8], rax
0x180006a67  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180006a6c  mov     ebx, eax
0x180006a6e  test    eax, eax
0x180006a70  js      loc_180006BC5
0x180006a76  mov     rax, [rbp+var_10]
0x180006a7a  mov     edx, [rax]
0x180006a7c  cmp     edx, 3FFFFFFFh
0x180006a82  jz      loc_180006BA8
0x180006a88  mov     rax, [rbp+var_18]
0x180006a8c  lea     rcx, [rbp+var_18]
0x180006a90  inc     edx
0x180006a92  mov     rax, [rax]
0x180006a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9a  mov     ebx, eax
0x180006a9c  test    eax, eax
0x180006a9e  js      short loc_180006B17
0x180006aa0  mov     rdx, [rbp+var_10]
0x180006aa4  mov     ecx, [rdx]
0x180006aa6  mov     rax, [rdx+8]
0x180006aaa  dec     ecx
0x180006aac  mov     rdx, r14; unsigned __int16 *
0x180006aaf  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180006ab5  lea     rcx, [rbp+var_18]; this
0x180006ab9  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x180006abe  mov     ebx, eax
0x180006ac0  test    eax, eax
0x180006ac2  js      loc_180006B8B
0x180006ac8  mov     rdx, [rbp+lpSubKey+8]; lpSubKey
0x180006acc  lea     rax, [rbp+arg_0]
0x180006ad0  mov     r9d, 20019h; samDesired
0x180006ad6  mov     qword ptr [rsp+60h+phkResult], rax; phkResult
0x180006adb  xor     r8d, r8d; ulOptions
0x180006ade  mov     [rbp+arg_0], 0
0x180006ae6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006aed  call    cs:__imp_RegOpenKeyExW
0x180006af3  mov     ebx, eax
0x180006af5  test    eax, eax
0x180006af7  jz      loc_180006B92
0x180006afd  add     eax, 0FFFFFFFEh
0x180006b00  cmp     eax, 1
0x180006b03  ja      loc_180006BB6
0x180006b09  mov     byte ptr [rdi], 0
0x180006b0c  mov     rcx, [rbp+arg_0]
0x180006b10  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180006b15  jmp     short loc_180006B66
0x180006b17  mov     rcx, [rbp+18h]; this
0x180006b1b  lea     r8, aOnecoreBaseApp_2; "onecore\\base\\appmodel\\common\\string"...
0x180006b22  mov     r9d, eax; char *
0x180006b25  mov     edx, 1Bh; void *
0x180006b2a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180006b2f  mov     edx, 497h; void *
0x180006b34  mov     rcx, [rbp+18h]; this
0x180006b38  lea     r8, aOnecoreAdminAp_19; "onecore\\admin\\appmodel\\appxalluserst"...
0x180006b3f  mov     r9d, ebx; char *
0x180006b42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006b47  mov     rcx, [rbp+lpSubKey+8]; void *
0x180006b4b  test    rcx, rcx
0x180006b4e  jz      short loc_180006B55
0x180006b50  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180006b55  mov     eax, ebx
0x180006b57  jmp     short loc_180006B76
0x180006b59  mov     rcx, [rbp+arg_0]
0x180006b5d  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180006b62  test    ebx, ebx
0x180006b64  js      short loc_180006BA1
0x180006b66  mov     rcx, [rbp+lpSubKey+8]; void *
0x180006b6a  test    rcx, rcx
0x180006b6d  jz      short loc_180006B74
0x180006b6f  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180006b74  xor     eax, eax
0x180006b76  lea     r11, [rsp+60h+var_s0]
0x180006b7b  mov     rbx, [r11+28h]
0x180006b7f  mov     rsi, [r11+30h]
0x180006b83  mov     rsp, r11
0x180006b86  pop     r14
0x180006b88  pop     rdi
0x180006b89  pop     rbp
0x180006b8a  retn
0x180006b8b  mov     edx, 498h
0x180006b90  jmp     short loc_180006B34
0x180006b92  mov     byte ptr [rdi], 1
0x180006b95  jmp     loc_180006B0C
0x180006b9a  mov     edx, 490h
0x180006b9f  jmp     short loc_180006B34
0x180006ba1  mov     edx, 49Bh
0x180006ba6  jmp     short loc_180006B34
0x180006ba8  mov     ebx, 80070503h
0x180006bad  jmp     short loc_180006B2F
0x180006baf  mov     eax, 80070057h
0x180006bb4  jmp     short loc_180006B76
0x180006bb6  test    ebx, ebx
0x180006bb8  jle     short loc_180006B59
0x180006bba  movzx   ebx, bx
0x180006bbd  or      ebx, 80070000h
0x180006bc3  jmp     short loc_180006B59
0x180006bc5  mov     rcx, [rbp+18h]; this
0x180006bc9  lea     r8, aOnecoreAdminAp_19; "onecore\\admin\\appmodel\\appxalluserst"...
0x180006bd0  mov     r9d, ebx; char *
0x180006bd3  mov     edx, 494h; void *
0x180006bd8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006bdd  lea     rcx, [rbp+lpSubKey]; this
0x180006be1  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180006be6  jmp     loc_180006B55
```
