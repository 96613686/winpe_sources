# RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::RcsChatRemoteContactComposingHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat *,Windows::Phone::Restricted::Cellular::Rcs::IRcsRemoteContactComposingEventArgs *)

- ea: `0x1800c27f0`
- end: `0x1800c2ac0`
- name: `?Invoke@RcsChatRemoteContactComposingHandler@?$RcsChatAdapterImplBase@VRcsGroupChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsGroupChat@23456@@@UEAAJPEAUIRcsGroupChat@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsRemoteContactComposingEventArgs@45678@@Z`
- size: `720`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000bae4`
- `0x180030bd0`
- `0x1800bbc88`
- `0x1800c27f0`
- `0x1800c466c`
- `0x1800c4a80`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c2920`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c2920`
- `PhoneUtil!GetDialStringFromTelUri` at `0x1800c29c4`
- `PhoneUtil!GetDialStringFromTelUri` at `0x1800c29c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c29ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c29ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c28b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c28f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2a7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c28b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c28f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c2a7f`

## string_xrefs

- `0x1800c284c`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x1800c288a`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`
- `0x1800c28df`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::RcsChatRemoteContactComposingHandler::Invoke(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rax
  int v6; // eax
  unsigned int v7; // edi
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  HRESULT DialStringFromTelUri; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  const wchar_t *v18; // r8
  const unsigned __int16 *StringRawBuffer; // rax
  wchar_t *v20; // rcx
  __int64 v21; // rdx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm1
  _BYTE v31[8]; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v35[288]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszDest[64]; // [rsp+170h] [rbp+70h] BYREF
  int v37; // [rsp+1F0h] [rbp+F0h]
  _DWORD v38[35]; // [rsp+1F4h] [rbp+F4h] BYREF
  __int128 v39; // [rsp+280h] [rbp+180h]

  v3 = *a3;
  v31[0] = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *))(v3 + 56))(a3, v31);
  v7 = v6;
  if ( v6 < 0 )
  {
    Log_HREvent_102(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
      138);
    return v7;
  }
  v9 = *a3;
  v34 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v9 + 48))(a3, &v34);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = v34;
    string = 0;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 128LL);
    WindowsDeleteString(0);
    string = 0;
    DialStringFromTelUri = v13(v12, &string);
    v11 = DialStringFromTelUri;
    if ( DialStringFromTelUri >= 0 )
    {
      if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
        McTemplateU0t_EventWriteTransfer(v16, v15, v31[0]);
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v37 = 0;
      memset(&v38[32], 0, 12);
      v39 = 0;
      memset_0(v38, 0, 0x80u);
      memset_0(pszDest, 0, sizeof(pszDest));
      v18 = *(const wchar_t **)(a1 + 128);
      v39 = *(_OWORD *)(a1 + 164);
      DialStringFromTelUri = StringCchCopyW(pszDest, 0x40u, v18);
      v11 = DialStringFromTelUri;
      if ( DialStringFromTelUri >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        DialStringFromTelUri = GetDialStringFromTelUri(StringRawBuffer, (unsigned __int16 *)v38, 0x40u);
        v11 = DialStringFromTelUri;
        if ( DialStringFromTelUri >= 0 )
        {
          v20 = pszDest;
          v37 = *(_DWORD *)(a1 + 160);
          v21 = 2;
          v38[32] = v31[0];
          *(struct _FILETIME *)&v38[33] = SystemTimeAsFileTime;
          v22 = v35;
          do
          {
            v23 = *((_OWORD *)v20 + 1);
            *v22 = *(_OWORD *)v20;
            v24 = *((_OWORD *)v20 + 2);
            v22[1] = v23;
            v25 = *((_OWORD *)v20 + 3);
            v22[2] = v24;
            v26 = *((_OWORD *)v20 + 4);
            v22[3] = v25;
            v27 = *((_OWORD *)v20 + 5);
            v22[4] = v26;
            v28 = *((_OWORD *)v20 + 6);
            v22[5] = v27;
            v29 = *((_OWORD *)v20 + 7);
            v20 += 64;
            v22[6] = v28;
            v22[7] = v29;
            v22 += 8;
            --v21;
          }
          while ( v21 );
          v30 = *((_OWORD *)v20 + 1);
          *v22 = *(_OWORD *)v20;
          v22[1] = v30;
          RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsRemoteContactComposingEventArgs,RcsRemoteContactComposingNotificationArgs>::_PublishNotifications(
            a1 - 8,
            v35);
          WindowsDeleteString(string);
          v11 = 0;
          goto LABEL_17;
        }
        v17 = 156;
      }
      else
      {
        v17 = 154;
      }
    }
    else
    {
      v17 = 144;
    }
    Log_HREvent_102(
      (unsigned int)DialStringFromTelUri,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
      v17);
    WindowsDeleteString(string);
LABEL_17:
    string = 0;
    goto LABEL_18;
  }
  Log_HREvent_102(
    (unsigned int)v10,
    1,
    "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
    141);
LABEL_18:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
  return v11;
}

```

## disassembly

```asm
0x1800c27f0  mov     [rsp-8+arg_8], rbx
0x1800c27f5  mov     [rsp-8+arg_18], rsi
0x1800c27fa  push    rbp
0x1800c27fb  push    rdi
0x1800c27fc  push    r14
0x1800c27fe  lea     rbp, [rsp-1A0h]
0x1800c2806  sub     rsp, 2A0h
0x1800c280d  mov     rax, cs:__security_cookie
0x1800c2814  xor     rax, rsp
0x1800c2817  mov     [rbp+1B0h+var_20], rax
0x1800c281e  mov     rax, [r8]
0x1800c2821  lea     rdx, [rsp+2B0h+var_280]
0x1800c2826  mov     rsi, rcx
0x1800c2829  xor     r14d, r14d
0x1800c282c  mov     rcx, r8
0x1800c282f  mov     [rsp+2B0h+var_280], r14b
0x1800c2834  mov     rbx, r8
0x1800c2837  mov     rax, [rax+38h]
0x1800c283b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2840  mov     edi, eax
0x1800c2842  test    eax, eax
0x1800c2844  jns     short loc_1800C2865
0x1800c2846  mov     r9d, 8Ah
0x1800c284c  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c2853  lea     edx, [r14+1]
0x1800c2857  mov     ecx, eax
0x1800c2859  call    Log_HREvent_102
0x1800c285e  mov     eax, edi
0x1800c2860  jmp     loc_1800C2A99
0x1800c2865  mov     rax, [rbx]
0x1800c2868  lea     rdx, [rsp+2B0h+var_268]
0x1800c286d  mov     rcx, rbx
0x1800c2870  mov     [rsp+2B0h+var_268], r14
0x1800c2875  mov     rax, [rax+30h]
0x1800c2879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c287e  mov     ebx, eax
0x1800c2880  test    eax, eax
0x1800c2882  jns     short loc_1800C28A2
0x1800c2884  mov     r9d, 8Dh
0x1800c288a  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c2891  mov     edx, 1
0x1800c2896  mov     ecx, eax
0x1800c2898  call    Log_HREvent_102
0x1800c289d  jmp     loc_1800C2A8D
0x1800c28a2  mov     rdi, [rsp+2B0h+var_268]
0x1800c28a7  xor     ecx, ecx; string
0x1800c28a9  mov     [rsp+2B0h+string], r14
0x1800c28ae  mov     rax, [rdi]
0x1800c28b1  mov     rbx, [rax+80h]
0x1800c28b8  call    cs:__imp_WindowsDeleteString
0x1800c28be  lea     rdx, [rsp+2B0h+string]
0x1800c28c3  mov     [rsp+2B0h+string], r14
0x1800c28c8  mov     rcx, rdi
0x1800c28cb  mov     rax, rbx
0x1800c28ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c28d3  mov     ebx, eax
0x1800c28d5  test    eax, eax
0x1800c28d7  jns     short loc_1800C2902
0x1800c28d9  mov     r9d, 90h
0x1800c28df  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c28e6  mov     edx, 1
0x1800c28eb  mov     ecx, eax
0x1800c28ed  call    Log_HREvent_102
0x1800c28f2  mov     rcx, [rsp+2B0h+string]; string
0x1800c28f7  call    cs:__imp_WindowsDeleteString
0x1800c28fd  jmp     loc_1800C2A88
0x1800c2902  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x1800c2909  jz      short loc_1800C2916
0x1800c290b  movzx   r8d, [rsp+2B0h+var_280]
0x1800c2911  call    McTemplateU0t_EventWriteTransfer
0x1800c2916  lea     rcx, [rsp+2B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800c291b  mov     qword ptr [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1800c2920  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c2926  xorps   xmm0, xmm0
0x1800c2929  mov     [rbp+1B0h+var_C0], r14d
0x1800c2930  mov     edi, 80h
0x1800c2935  mov     [rbp+1B0h+var_3C], r14
0x1800c293c  mov     r8d, edi; Size
0x1800c293f  mov     [rbp+1B0h+var_34], r14d
0x1800c2946  xor     edx, edx; Val
0x1800c2948  lea     rcx, [rbp+1B0h+var_BC]; void *
0x1800c294f  movups  [rbp+1B0h+var_30], xmm0
0x1800c2956  call    memset_0
0x1800c295b  mov     r8d, edi; Size
0x1800c295e  lea     rcx, [rbp+1B0h+pszDest]; void *
0x1800c2962  xor     edx, edx; Val
0x1800c2964  call    memset_0
0x1800c2969  mov     rax, [rsi+0A4h]
0x1800c2970  lea     edx, [rdi-40h]; cchDest
0x1800c2973  mov     r8, [rsi+80h]; pszSrc
0x1800c297a  lea     rcx, [rbp+1B0h+pszDest]; pszDest
0x1800c297e  mov     qword ptr [rbp+1B0h+var_30], rax
0x1800c2985  mov     rax, [rsi+0ACh]
0x1800c298c  mov     qword ptr [rbp+1B0h+var_30+8], rax
0x1800c2993  call    StringCchCopyW
0x1800c2998  mov     ebx, eax
0x1800c299a  test    eax, eax
0x1800c299c  jns     short loc_1800C29A7
0x1800c299e  lea     r9d, [rdi+1Ah]
0x1800c29a2  jmp     loc_1800C28DF
0x1800c29a7  mov     rcx, [rsp+2B0h+string]; string
0x1800c29ac  xor     edx, edx; length
0x1800c29ae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c29b4  mov     r8d, 40h ; '@'
0x1800c29ba  lea     rdx, [rbp+1B0h+var_BC]
0x1800c29c1  mov     rcx, rax
0x1800c29c4  call    cs:__imp_?GetDialStringFromTelUri@@YAJPEBGPEAGI@Z; GetDialStringFromTelUri(ushort const *,ushort *,uint)
0x1800c29ca  mov     ebx, eax
0x1800c29cc  test    eax, eax
0x1800c29ce  jns     short loc_1800C29DB
0x1800c29d0  mov     r9d, 9Ch
0x1800c29d6  jmp     loc_1800C28DF
0x1800c29db  mov     eax, [rsi+0A0h]
0x1800c29e1  lea     rcx, [rbp+1B0h+pszDest]
0x1800c29e5  mov     [rbp+1B0h+var_C0], eax
0x1800c29eb  mov     edx, 2
0x1800c29f0  movzx   eax, [rsp+2B0h+var_280]
0x1800c29f5  mov     dword ptr [rbp+1B0h+var_3C], eax
0x1800c29fb  mov     eax, [rsp+2B0h+SystemTimeAsFileTime.dwLowDateTime]
0x1800c29ff  mov     dword ptr [rbp+1B0h+var_3C+4], eax
0x1800c2a05  mov     eax, [rsp+2B0h+SystemTimeAsFileTime.dwHighDateTime]
0x1800c2a09  mov     [rbp+1B0h+var_34], eax
0x1800c2a0f  lea     rax, [rsp+2B0h+var_260]
0x1800c2a14  movups  xmm0, xmmword ptr [rcx]
0x1800c2a17  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c2a1b  movups  xmmword ptr [rax], xmm0
0x1800c2a1e  movups  xmm0, xmmword ptr [rcx+20h]
0x1800c2a22  movups  xmmword ptr [rax+10h], xmm1
0x1800c2a26  movups  xmm1, xmmword ptr [rcx+30h]
0x1800c2a2a  movups  xmmword ptr [rax+20h], xmm0
0x1800c2a2e  movups  xmm0, xmmword ptr [rcx+40h]
0x1800c2a32  movups  xmmword ptr [rax+30h], xmm1
0x1800c2a36  movups  xmm1, xmmword ptr [rcx+50h]
0x1800c2a3a  movups  xmmword ptr [rax+40h], xmm0
0x1800c2a3e  movups  xmm0, xmmword ptr [rcx+60h]
0x1800c2a42  movups  xmmword ptr [rax+50h], xmm1
0x1800c2a46  movups  xmm1, xmmword ptr [rcx+70h]
0x1800c2a4a  add     rcx, rdi
0x1800c2a4d  movups  xmmword ptr [rax+60h], xmm0
0x1800c2a51  movups  xmmword ptr [rax+70h], xmm1
0x1800c2a55  add     rax, rdi
0x1800c2a58  sub     rdx, 1
0x1800c2a5c  jnz     short loc_1800C2A14
0x1800c2a5e  movups  xmm0, xmmword ptr [rcx]
0x1800c2a61  lea     rdx, [rsp+2B0h+var_260]
0x1800c2a66  movups  xmm1, xmmword ptr [rcx+10h]
0x1800c2a6a  lea     rcx, [rsi-8]
0x1800c2a6e  movups  xmmword ptr [rax], xmm0
0x1800c2a71  movups  xmmword ptr [rax+10h], xmm1
0x1800c2a75  call    ?_PublishNotifications@?$RcsEventHandler@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@VRcsRemoteContactComposingEventArgs@23456@URcsRemoteContactComposingNotificationArgs@@@@IEAAXURcsRemoteContactComposingNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsRemoteContactComposingEventArgs,RcsRemoteContactComposingNotificationArgs>::_PublishNotifications(RcsRemoteContactComposingNotificationArgs)
0x1800c2a7a  mov     rcx, [rsp+2B0h+string]; string
0x1800c2a7f  call    cs:__imp_WindowsDeleteString
0x1800c2a85  mov     ebx, r14d
0x1800c2a88  mov     [rsp+2B0h+string], r14
0x1800c2a8d  lea     rcx, [rsp+2B0h+var_268]
0x1800c2a92  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c2a97  mov     eax, ebx
0x1800c2a99  mov     rcx, [rbp+1B0h+var_20]
0x1800c2aa0  xor     rcx, rsp; StackCookie
0x1800c2aa3  call    __security_check_cookie
0x1800c2aa8  lea     r11, [rsp+2B0h+var_10]
0x1800c2ab0  mov     rbx, [r11+28h]
0x1800c2ab4  mov     rsi, [r11+38h]
0x1800c2ab8  mov     rsp, r11
0x1800c2abb  pop     r14
0x1800c2abd  pop     rdi
0x1800c2abe  pop     rbp
0x1800c2abf  retn
```
