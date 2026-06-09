# RunAsComServer

- ea: `0x140017cb8`
- end: `0x140017e7c`
- name: `RunAsComServer`
- size: `452`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x140007c44`
- `0x140009594`
- `0x1400095b4`
- `0x14000a6a8`
- `0x14000b2c8`
- `0x14000bd24`
- `0x14000c5dc`
- `0x1400126c8`
- `0x140017cb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140017dee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140017dee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140017d56`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140017d56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017db9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017e0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017db9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017e0f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 RunAsComServer()
{
  HANDLE EventW; // rax
  const char *v1; // r9
  void *v2; // rbx
  unsigned int LastError; // edi
  unsigned int v4; // r8d
  const char *v5; // r9
  DWORD v7; // eax
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int v10; // r8d
  const char *v11; // r9
  int v12; // [rsp+20h] [rbp-49h]
  char v13; // [rsp+20h] [rbp-49h]
  void **v14; // [rsp+30h] [rbp-39h] BYREF
  __int64 v15; // [rsp+38h] [rbp-31h]
  __int64 v16; // [rsp+40h] [rbp-29h]
  _OWORD v17[2]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v18; // [rsp+68h] [rbp-1h]
  __int64 v19; // [rsp+70h] [rbp+7h]
  unsigned int v20; // [rsp+80h] [rbp+17h] BYREF
  _BYTE v21[4]; // [rsp+84h] [rbp+1Bh] BYREF
  char *v22; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  LOBYTE(v12) = ATL::_pAtlModule != 0;
  memset(v17, 0, sizeof(v17));
  v18 = 0;
  v15 = 0;
  v16 = 0;
  ATL::_pAtlModule = (struct ATL::CAtlModule *)&v14;
  v19 = 0;
  if ( (int)ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)v17) >= 0 )
    LODWORD(v15) = 56;
  v14 = &ATL::CComModule::`vftable';
  if ( !ATL::_pAtlModule )
    ATL::_pAtlModule = (struct ATL::CAtlModule *)&v14;
  EventW = CreateEventW(0, 0, 0, 0);
  v2 = EventW;
  if ( !EventW )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x200,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
                  v1);
    if ( (_BYTE)v12 )
      ATL::_pAtlModule = 0;
LABEL_12:
    v14 = &ATL::CComModule::`vftable';
    ATL::CAtlModule::~CAtlModule((ATL::CAtlModule *)&v14);
    return LastError;
  }
  AutoMdm::RegisterComServerWrapper<AutoMdmNotificationCallback>::RegisterComServerWrapper<AutoMdmNotificationCallback>(
    &v20,
    EventW);
  LastError = (unsigned int)v22;
  if ( (int)v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\exe\\main.cpp",
      (const char *)(unsigned int)v22,
      v12);
    if ( !CloseHandle(v2) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
    if ( v13 )
      ATL::_pAtlModule = 0;
    goto LABEL_12;
  }
  v7 = WaitForSingleObjectEx(v2, 0xFFFFFFFF, 0);
  if ( v7 != 258 && v7 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB0F, v8, v9);
  details::UnRegisterActivator<1>(v21, v20);
  if ( !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
  if ( (_BYTE)v12 )
    ATL::_pAtlModule = 0;
  v14 = &ATL::CComModule::`vftable';
  ATL::CAtlModule::~CAtlModule((ATL::CAtlModule *)&v14);
  return 0;
}

```

## disassembly

```asm
0x140017cb8  push    rbp
0x140017cba  push    rbx
0x140017cbb  push    rsi
0x140017cbc  push    rdi
0x140017cbd  push    r14
0x140017cbf  lea     rbp, [rsp-37h]
0x140017cc4  sub     rsp, 0A0h
0x140017ccb  mov     rax, cs:__security_cookie
0x140017cd2  xor     rax, rsp
0x140017cd5  mov     [rbp+57h+var_30], rax
0x140017cd9  xor     esi, esi
0x140017cdb  cmp     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rsi; ATL::CAtlModule * ATL::_pAtlModule
0x140017ce2  setnz   [rbp+57h+var_A0]
0x140017ce6  lea     rax, ?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140017ced  mov     [rbp+57h+var_98], rax
0x140017cf1  xorps   xmm0, xmm0
0x140017cf4  xor     eax, eax
0x140017cf6  movups  [rbp+57h+var_78], xmm0
0x140017cfa  movups  [rbp+57h+var_68], xmm0
0x140017cfe  mov     [rbp+57h+var_58], rax
0x140017d02  mov     [rbp+57h+var_88], rsi
0x140017d06  mov     [rbp+57h+var_80], rsi
0x140017d0a  lea     rax, [rbp+57h+var_90]
0x140017d0e  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rax; ATL::CAtlModule * ATL::_pAtlModule
0x140017d15  mov     [rbp+57h+var_50], rsi
0x140017d19  lea     rcx, [rbp+57h+var_78]; this
0x140017d1d  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140017d22  test    eax, eax
0x140017d24  js      short loc_140017D2D
0x140017d26  mov     dword ptr [rbp+57h+var_88], 38h ; '8'
0x140017d2d  lea     r14, ??_7CComModule@ATL@@6B@; const ATL::CComModule::`vftable'
0x140017d34  mov     [rbp+57h+var_90], r14
0x140017d38  cmp     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rsi; ATL::CAtlModule * ATL::_pAtlModule
0x140017d3f  jnz     short loc_140017D4C
0x140017d41  lea     rax, [rbp+57h+var_90]
0x140017d45  mov     cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA, rax; ATL::CAtlModule * ATL::_pAtlModule
0x140017d4c  xor     r9d, r9d; lpName
0x140017d4f  xor     r8d, r8d; bInitialState
0x140017d52  xor     edx, edx; bManualReset
0x140017d54  xor     ecx, ecx; lpEventAttributes
0x140017d56  call    cs:__imp_CreateEventW
0x140017d5c  mov     rbx, rax
0x140017d5f  test    rax, rax
0x140017d62  jnz     short loc_140017D8A
0x140017d64  mov     rcx, [rbp+5Fh]; this
0x140017d68  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140017d6f  mov     edx, 200h; void *
0x140017d74  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140017d79  mov     edi, eax
0x140017d7b  cmp     [rbp+57h+var_A0], sil
0x140017d7f  jz      short loc_140017DD4
0x140017d81  mov     rax, [rbp+57h+var_98]
0x140017d85  mov     [rax], rsi
0x140017d88  jmp     short loc_140017DD4
0x140017d8a  mov     rdx, rbx
0x140017d8d  lea     rcx, [rbp+57h+var_40]
0x140017d91  call    ??0?$RegisterComServerWrapper@VAutoMdmNotificationCallback@@@AutoMdm@@QEAA@PEAXK@Z; AutoMdm::RegisterComServerWrapper<AutoMdmNotificationCallback>::RegisterComServerWrapper<AutoMdmNotificationCallback>(void *,ulong)
0x140017d96  mov     edi, dword ptr [rbp+57h+var_38]
0x140017d99  test    edi, edi
0x140017d9b  jns     short loc_140017DE5
0x140017d9d  mov     rcx, [rbp+5Fh]; this
0x140017da1  mov     r9d, edi; char *
0x140017da4  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140017dab  mov     edx, 203h; void *
0x140017db0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017db5  nop
0x140017db6  mov     rcx, rbx; hObject
0x140017db9  call    cs:__imp_CloseHandle
0x140017dbf  test    eax, eax
0x140017dc1  jz      loc_140017E5E
0x140017dc7  cmp     [rbp+57h+var_A0], sil
0x140017dcb  jz      short loc_140017DD4
0x140017dcd  mov     rcx, [rbp+57h+var_98]
0x140017dd1  mov     [rcx], rsi
0x140017dd4  mov     [rbp+57h+var_90], r14
0x140017dd8  lea     rcx, [rbp+57h+var_90]; this
0x140017ddc  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x140017de1  mov     eax, edi
0x140017de3  jmp     short loc_140017E35
0x140017de5  xor     r8d, r8d; bAlertable
0x140017de8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140017deb  mov     rcx, rbx; hHandle
0x140017dee  call    cs:__imp_WaitForSingleObjectEx
0x140017df4  cmp     eax, 102h
0x140017df9  jz      short loc_140017DFF
0x140017dfb  test    eax, eax
0x140017dfd  jnz     short loc_140017E6D
0x140017dff  mov     edx, [rbp+57h+var_40]
0x140017e02  lea     rcx, [rbp+57h+var_3C]
0x140017e06  call    ??$UnRegisterActivator@$00@details@@YAJPEAKK@Z; details::UnRegisterActivator<1>(ulong *,ulong)
0x140017e0b  nop
0x140017e0c  mov     rcx, rbx; hObject
0x140017e0f  call    cs:__imp_CloseHandle
0x140017e15  test    eax, eax
0x140017e17  jz      short loc_140017E4F
0x140017e19  cmp     [rbp+57h+var_A0], sil
0x140017e1d  jz      short loc_140017E26
0x140017e1f  mov     rax, [rbp+57h+var_98]
0x140017e23  mov     [rax], rsi
0x140017e26  mov     [rbp+57h+var_90], r14
0x140017e2a  lea     rcx, [rbp+57h+var_90]; this
0x140017e2e  call    ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
0x140017e33  xor     eax, eax
0x140017e35  mov     rcx, [rbp+57h+var_30]
0x140017e39  xor     rcx, rsp; StackCookie
0x140017e3c  call    __security_check_cookie
0x140017e41  add     rsp, 0A0h
0x140017e48  pop     r14
0x140017e4a  pop     rdi
0x140017e4b  pop     rsi
0x140017e4c  pop     rbx
0x140017e4d  pop     rbp
0x140017e4e  retn
0x140017e4f  mov     rcx, [rbp+5Fh]; this
0x140017e53  mov     edx, 0A0Bh; void *
0x140017e58  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140017e5e  mov     rcx, [rbp+5Fh]; this
0x140017e62  mov     edx, 0A0Bh; void *
0x140017e67  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140017e6d  mov     rcx, [rbp+5Fh]; this
0x140017e71  mov     edx, 0B0Fh; void *
0x140017e76  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
