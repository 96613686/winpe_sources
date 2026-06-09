# _Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan_::_3_::_lambda_1_::operator()

- ea: `0x18002aaa8`
- end: `0x18002add7`
- name: `_Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan_::_3_::_lambda_1_::operator()`
- size: `815`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180043f10`

## callees

- `0x180008c84`
- `0x18000efa4`
- `0x180017e08`
- `0x18001bd80`
- `0x18001bfa8`
- `0x1800242fc`
- `0x18002aaa8`
- `0x18003cf80`
- `0x18003e760`
- `0x180040ea8`
- `0x18004491c`
- `0x1800449d8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002abce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002abe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002ac2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002accc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002acde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002ad29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002abce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002abe0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002ac2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002accc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002acde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002ad29`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002adb9`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x18002adb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan_::_3_::_lambda_1_::operator()(
        Windows::Networking::UX::Internal::MBCategory **a1)
{
  int WwanInterfaceObject; // ebx
  Windows::Networking::UX::Internal::MBCategory *v3; // rcx
  unsigned int v4; // edx
  unsigned int v5; // eax
  unsigned int v6; // edi
  int v7; // r9d
  __int64 v8; // r12
  unsigned int i; // r14d
  __int64 v10; // rbx
  __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r12
  unsigned int v15; // r14d
  __int64 v16; // r15
  __int64 v17; // r13
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  HSTRING string[2]; // [rsp+20h] [rbp-40h] BYREF
  HSTRING v23[2]; // [rsp+30h] [rbp-30h] BYREF
  __int128 v24; // [rsp+40h] [rbp-20h] BYREF
  __int128 v25; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 v27; // [rsp+A0h] [rbp+40h] BYREF
  unsigned __int64 v28; // [rsp+A8h] [rbp+48h] BYREF

  Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::Clear(*((_QWORD *)*a1 + 99));
  v27 = 0;
  string[0] = (HSTRING)&v27;
  string[1] = 0;
  LOBYTE(v23[0]) = 1;
  WwanInterfaceObject = Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(
                          *a1,
                          (struct WWAN_INTERFACE_OBJECT **)&string[1]);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>((__int64 **)string);
  if ( WwanInterfaceObject >= 0 && v27 )
  {
    if ( *(_DWORD *)(v27 + 1436) == 1 )
    {
      v4 = *(_DWORD *)(v27 + 1424);
      if ( v4 )
      {
        v5 = Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(v3, v4);
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x512,
          (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\mbcategory.cpp",
          (const char *)v5,
          (int)string[0]);
      }
      else
      {
        v6 = *(_DWORD *)(v27 + 1412);
        v7 = *(_DWORD *)(v27 + 1408);
        if ( v7 == 2 )
        {
          v8 = v27 + *(_QWORD *)(v27 + 1416);
          for ( i = 0; i < v6; ++i )
          {
            *(_OWORD *)string = 0;
            *(_OWORD *)v23 = 0;
            v10 = 68LL * i;
            LODWORD(string[0]) = Windows::Networking::UX::Internal::MBCategory::_MbDataClassFlagsFromWwanDataClasses(
                                   v3,
                                   *(unsigned int *)(v10 + v8 + 64));
            HIDWORD(string[0]) = Windows::Networking::UX::Internal::MBCategory::_OperatorStatusFromWwan(
                                   v11,
                                   *(unsigned int *)(v10 + v8 + 16));
            WindowsCreateString((PCNZWCH)(v10 + v8 + 20), 0x15u, &string[1]);
            WindowsCreateString((PCNZWCH)(v10 + v8), 7u, v23);
            v28 = 0;
            if ( (int)StringCchLengthW((const unsigned __int16 *)(v10 + v8), v12, &v28) >= 0 )
            {
              if ( v28 >= 3 )
                WindowsCreateString((PCNZWCH)(v10 + v8), 3u, &v23[1]);
              v24 = *(_OWORD *)string;
              v25 = *(_OWORD *)v23;
              LOBYTE(v13) = 1;
              Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::InsertAtInternal(
                *((_QWORD *)*a1 + 99),
                0,
                &v24,
                v13);
            }
            else
            {
              MBSettingUXLogging::Error(
                "Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan::<lambda_1>::operator ()",
                0x52Cu,
                "Failed to do StringCchLength");
            }
          }
        }
        else if ( v7 == 10 )
        {
          v14 = v27 + *(_QWORD *)(v27 + 1416);
          v15 = 0;
          if ( v6 )
          {
            v16 = 0;
            do
            {
              *(_OWORD *)string = 0;
              *(_OWORD *)v23 = 0;
              v17 = 80 * v16 + v14;
              LODWORD(string[0]) = Windows::Networking::UX::Internal::MBCategory::_MbDataClassFlagsFromWwanDataClasses(
                                     v3,
                                     *(unsigned int *)(v17 + 64));
              HIDWORD(string[0]) = Windows::Networking::UX::Internal::MBCategory::_OperatorStatusFromWwan(
                                     v18,
                                     *(unsigned int *)(v17 + 16));
              WindowsCreateString((PCNZWCH)(80 * v16 + v14 + 20), 0x15u, &string[1]);
              WindowsCreateString((PCNZWCH)v17, 7u, v23);
              v28 = 0;
              if ( (int)StringCchLengthW((const unsigned __int16 *)v17, v19, &v28) >= 0 )
              {
                if ( v28 >= 3 )
                  WindowsCreateString((PCNZWCH)(80 * v16 + v14), 3u, &v23[1]);
                v24 = *(_OWORD *)string;
                v25 = *(_OWORD *)v23;
                LOBYTE(v20) = 1;
                Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::InsertAtInternal(
                  *((_QWORD *)*a1 + 99),
                  0,
                  &v24,
                  v20);
              }
              else
              {
                MBSettingUXLogging::Error(
                  "Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan::<lambda_1>::operator ()",
                  0x54Cu,
                  "Failed to do StringCchLength");
              }
              ++v15;
              ++v16;
            }
            while ( v15 < v6 );
          }
        }
        else
        {
          MBSettingUXLogging::Error(
            "Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan::<lambda_1>::operator ()",
            0x55Au,
            "Failed to do GetWwanInterfaceObject. ElementType=%d");
        }
      }
    }
    else
    {
      MBSettingUXLogging::Error(
        "Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan::<lambda_1>::operator ()",
        0x50Eu,
        "Unexpected scanResultType. scanResultType=%d");
    }
    Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(*a1, 8);
  }
  else
  {
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBCategory::ProcessNetworkScan::<lambda_1>::operator ()",
      0x562u,
      "Failed to do GetWwanInterfaceObject");
  }
  v21 = v27;
  v27 = 0;
  if ( v21 )
    WwanFreeMemory(v21);
}

```

## disassembly

```asm
0x18002aaa8  mov     [rsp-38h+arg_10], rbx
0x18002aaad  push    rbp
0x18002aaae  push    rsi
0x18002aaaf  push    rdi
0x18002aab0  push    r12
0x18002aab2  push    r13
0x18002aab4  push    r14
0x18002aab6  push    r15
0x18002aab8  mov     rbp, rsp
0x18002aabb  sub     rsp, 60h
0x18002aabf  mov     rsi, rcx
0x18002aac2  mov     rcx, [rcx]
0x18002aac5  mov     rcx, [rcx+318h]
0x18002aacc  call    ?Clear@?$Vector@UMbOperatorInfo@UX@Networking@Windows@@UMboEqualityPredicate@Internal@234@UMboLifetimePredicate@6234@U?$VectorOptions@UMbOperatorInfo@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@UEAAJXZ; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::Clear(void)
0x18002aad1  mov     [rbp+arg_0], 0
0x18002aad9  lea     rax, [rbp+arg_0]
0x18002aadd  mov     [rbp+string], rax
0x18002aae1  mov     [rbp+string+8], 0
0x18002aae9  mov     byte ptr [rbp+var_30], 1
0x18002aaed  lea     rdx, [rbp+string+8]; struct WWAN_INTERFACE_OBJECT **
0x18002aaf1  mov     rcx, [rsi]; this
0x18002aaf4  call    ?_GetWwanInterfaceObject@MBCategory@Internal@UX@Networking@Windows@@AEAAJPEAPEAUWWAN_INTERFACE_OBJECT@@@Z; Windows::Networking::UX::Internal::MBCategory::_GetWwanInterfaceObject(WWAN_INTERFACE_OBJECT * *)
0x18002aaf9  mov     ebx, eax
0x18002aafb  lea     rcx, [rbp+string]
0x18002aaff  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18002ab04  test    ebx, ebx
0x18002ab06  js      loc_18002AD8F
0x18002ab0c  mov     rax, [rbp+arg_0]
0x18002ab10  test    rax, rax
0x18002ab13  jz      loc_18002AD8F
0x18002ab19  mov     r9d, [rax+59Ch]
0x18002ab20  cmp     r9d, 1
0x18002ab24  jz      short loc_18002AB37
0x18002ab26  lea     r8, aUnexpectedScan; "Unexpected scanResultType. scanResultTy"...
0x18002ab2d  mov     edx, 50Eh
0x18002ab32  jmp     loc_18002AD74
0x18002ab37  mov     edx, [rax+590h]; unsigned int
0x18002ab3d  test    edx, edx
0x18002ab3f  jz      short loc_18002AB63
0x18002ab41  call    ?_HResultFromWwanStatus@MBCategory@Internal@UX@Networking@Windows@@AEAAJK@Z; Windows::Networking::UX::Internal::MBCategory::_HResultFromWwanStatus(ulong)
0x18002ab46  mov     rcx, [rbp+38h]; this
0x18002ab4a  mov     r9d, eax; char *
0x18002ab4d  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x18002ab54  mov     edx, 512h; void *
0x18002ab59  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002ab5e  jmp     loc_18002AD80
0x18002ab63  mov     edi, [rax+584h]
0x18002ab69  mov     r9d, [rax+580h]
0x18002ab70  cmp     r9d, 2
0x18002ab74  jnz     loc_18002AC6A
0x18002ab7a  mov     r12, [rax+588h]
0x18002ab81  add     r12, rax
0x18002ab84  xor     r14d, r14d
0x18002ab87  test    edi, edi
0x18002ab89  jz      loc_18002AD80
0x18002ab8f  xorps   xmm0, xmm0
0x18002ab92  movups  xmmword ptr [rbp+string], xmm0
0x18002ab96  movups  xmmword ptr [rbp+var_30], xmm0
0x18002ab9a  mov     eax, r14d
0x18002ab9d  imul    rbx, rax, 44h ; 'D'
0x18002aba1  lea     r15, [rbx+r12]
0x18002aba5  mov     edx, [r15+40h]
0x18002aba9  call    ?_MbDataClassFlagsFromWwanDataClasses@MBCategory@Internal@UX@Networking@Windows@@AEAA?AW4MbDataClassFlags@345@K@Z; Windows::Networking::UX::Internal::MBCategory::_MbDataClassFlagsFromWwanDataClasses(ulong)
0x18002abae  mov     dword ptr [rbp+string], eax
0x18002abb1  mov     edx, [r15+10h]
0x18002abb5  call    ?_OperatorStatusFromWwan@MBCategory@Internal@UX@Networking@Windows@@AEAA?AW4MbOperatorStatus@345@K@Z; Windows::Networking::UX::Internal::MBCategory::_OperatorStatusFromWwan(ulong)
0x18002abba  mov     dword ptr [rbp+string+4], eax
0x18002abbd  lea     rcx, [r12+14h]
0x18002abc2  add     rcx, rbx; sourceString
0x18002abc5  lea     r8, [rbp+string+8]; string
0x18002abc9  mov     edx, 15h; length
0x18002abce  call    cs:__imp_WindowsCreateString
0x18002abd4  lea     r8, [rbp+var_30]; string
0x18002abd8  mov     edx, 7; length
0x18002abdd  mov     rcx, r15; sourceString
0x18002abe0  call    cs:__imp_WindowsCreateString
0x18002abe6  mov     [rbp+arg_8], 0
0x18002abee  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18002abf2  mov     rcx, r15; unsigned __int16 *
0x18002abf5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002abfa  test    eax, eax
0x18002abfc  jns     short loc_18002AC18
0x18002abfe  lea     r8, aFailedToDoStri; "Failed to do StringCchLength"
0x18002ac05  mov     edx, 52Ch; unsigned int
0x18002ac0a  lea     rcx, aWindowsNetwork_208; "Windows::Networking::UX::Internal::MBCa"...
0x18002ac11  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18002ac16  jmp     short loc_18002AC59
0x18002ac18  cmp     [rbp+arg_8], 3
0x18002ac1d  jb      short loc_18002AC31
0x18002ac1f  lea     r8, [rbp+var_30+8]; string
0x18002ac23  mov     edx, 3; length
0x18002ac28  mov     rcx, r15; sourceString
0x18002ac2b  call    cs:__imp_WindowsCreateString
0x18002ac31  movups  xmm0, xmmword ptr [rbp+string]
0x18002ac35  movaps  [rbp+var_20], xmm0
0x18002ac39  movups  xmm1, xmmword ptr [rbp+var_30]
0x18002ac3d  movaps  [rbp+var_10], xmm1
0x18002ac41  mov     rcx, [rsi]
0x18002ac44  mov     r9b, 1
0x18002ac47  lea     r8, [rbp+var_20]
0x18002ac4b  xor     edx, edx
0x18002ac4d  mov     rcx, [rcx+318h]
0x18002ac54  call    ?InsertAtInternal@?$Vector@UMbOperatorInfo@UX@Networking@Windows@@UMboEqualityPredicate@Internal@234@UMboLifetimePredicate@6234@U?$VectorOptions@UMbOperatorInfo@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUMbOperatorInfo@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::MbOperatorInfo,bool)
0x18002ac59  inc     r14d
0x18002ac5c  cmp     r14d, edi
0x18002ac5f  jb      loc_18002AB8F
0x18002ac65  jmp     loc_18002AD80
0x18002ac6a  cmp     r9d, 0Ah
0x18002ac6e  jnz     loc_18002AD68
0x18002ac74  mov     r12, [rax+588h]
0x18002ac7b  add     r12, rax
0x18002ac7e  xor     r14d, r14d
0x18002ac81  test    edi, edi
0x18002ac83  jz      loc_18002AD80
0x18002ac89  xor     r15d, r15d
0x18002ac8c  xorps   xmm0, xmm0
0x18002ac8f  movups  xmmword ptr [rbp+string], xmm0
0x18002ac93  movups  xmmword ptr [rbp+var_30], xmm0
0x18002ac97  lea     rbx, [r15+r15*4]
0x18002ac9b  shl     rbx, 4
0x18002ac9f  lea     r13, [rbx+r12]
0x18002aca3  mov     edx, [r13+40h]
0x18002aca7  call    ?_MbDataClassFlagsFromWwanDataClasses@MBCategory@Internal@UX@Networking@Windows@@AEAA?AW4MbDataClassFlags@345@K@Z; Windows::Networking::UX::Internal::MBCategory::_MbDataClassFlagsFromWwanDataClasses(ulong)
0x18002acac  mov     dword ptr [rbp+string], eax
0x18002acaf  mov     edx, [r13+10h]
0x18002acb3  call    ?_OperatorStatusFromWwan@MBCategory@Internal@UX@Networking@Windows@@AEAA?AW4MbOperatorStatus@345@K@Z; Windows::Networking::UX::Internal::MBCategory::_OperatorStatusFromWwan(ulong)
0x18002acb8  mov     dword ptr [rbp+string+4], eax
0x18002acbb  lea     rcx, [r12+14h]
0x18002acc0  add     rcx, rbx; sourceString
0x18002acc3  lea     r8, [rbp+string+8]; string
0x18002acc7  mov     edx, 15h; length
0x18002accc  call    cs:__imp_WindowsCreateString
0x18002acd2  lea     r8, [rbp+var_30]; string
0x18002acd6  mov     edx, 7; length
0x18002acdb  mov     rcx, r13; sourceString
0x18002acde  call    cs:__imp_WindowsCreateString
0x18002ace4  mov     [rbp+arg_8], 0
0x18002acec  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18002acf0  mov     rcx, r13; unsigned __int16 *
0x18002acf3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002acf8  test    eax, eax
0x18002acfa  jns     short loc_18002AD16
0x18002acfc  lea     r8, aFailedToDoStri; "Failed to do StringCchLength"
0x18002ad03  mov     edx, 54Ch; unsigned int
0x18002ad08  lea     rcx, aWindowsNetwork_208; "Windows::Networking::UX::Internal::MBCa"...
0x18002ad0f  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18002ad14  jmp     short loc_18002AD57
0x18002ad16  cmp     [rbp+arg_8], 3
0x18002ad1b  jb      short loc_18002AD2F
0x18002ad1d  lea     r8, [rbp+var_30+8]; string
0x18002ad21  mov     edx, 3; length
0x18002ad26  mov     rcx, r13; sourceString
0x18002ad29  call    cs:__imp_WindowsCreateString
0x18002ad2f  movups  xmm0, xmmword ptr [rbp+string]
0x18002ad33  movaps  [rbp+var_20], xmm0
0x18002ad37  movups  xmm1, xmmword ptr [rbp+var_30]
0x18002ad3b  movaps  [rbp+var_10], xmm1
0x18002ad3f  mov     rcx, [rsi]
0x18002ad42  mov     r9b, 1
0x18002ad45  lea     r8, [rbp+var_20]
0x18002ad49  xor     edx, edx
0x18002ad4b  mov     rcx, [rcx+318h]
0x18002ad52  call    ?InsertAtInternal@?$Vector@UMbOperatorInfo@UX@Networking@Windows@@UMboEqualityPredicate@Internal@234@UMboLifetimePredicate@6234@U?$VectorOptions@UMbOperatorInfo@UX@Networking@Windows@@$0A@$00$0A@@6Collections@Foundation@4@@Internal@Collections@Foundation@Windows@@AEAAJIUMbOperatorInfo@UX@Networking@5@_N@Z; Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::MbOperatorInfo,Windows::Networking::UX::Internal::MboEqualityPredicate,Windows::Networking::UX::Internal::MboLifetimePredicate,Windows::Foundation::Collections::Internal::VectorOptions<Windows::Networking::UX::MbOperatorInfo,0,1,0>>::InsertAtInternal(uint,Windows::Networking::UX::MbOperatorInfo,bool)
0x18002ad57  inc     r14d
0x18002ad5a  inc     r15
0x18002ad5d  cmp     r14d, edi
0x18002ad60  jb      loc_18002AC8C
0x18002ad66  jmp     short loc_18002AD80
0x18002ad68  lea     r8, aFailedToDoGetw_0; "Failed to do GetWwanInterfaceObject. El"...
0x18002ad6f  mov     edx, 55Ah; unsigned int
0x18002ad74  lea     rcx, aWindowsNetwork_208; "Windows::Networking::UX::Internal::MBCa"...
0x18002ad7b  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18002ad80  mov     edx, 8
0x18002ad85  mov     rcx, [rsi]
0x18002ad88  call    ?_SubmitThreadpoolInvoke@MBCategory@Internal@UX@Networking@Windows@@AEAAJW4MbInterfaceChangeProperty@345@@Z; Windows::Networking::UX::Internal::MBCategory::_SubmitThreadpoolInvoke(Windows::Networking::UX::MbInterfaceChangeProperty)
0x18002ad8d  jmp     short loc_18002ADA8
0x18002ad8f  lea     r8, aFailedToDoGetw; "Failed to do GetWwanInterfaceObject"
0x18002ad96  mov     edx, 562h; unsigned int
0x18002ad9b  lea     rcx, aWindowsNetwork_208; "Windows::Networking::UX::Internal::MBCa"...
0x18002ada2  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18002ada7  nop
0x18002ada8  mov     rcx, [rbp+arg_0]
0x18002adac  mov     [rbp+arg_0], 0
0x18002adb4  test    rcx, rcx
0x18002adb7  jz      short loc_18002ADBF
0x18002adb9  call    cs:__imp_WwanFreeMemory
0x18002adbf  mov     rbx, [rsp+60h+arg_10]
0x18002adc7  add     rsp, 60h
0x18002adcb  pop     r15
0x18002adcd  pop     r14
0x18002adcf  pop     r13
0x18002add1  pop     r12
0x18002add3  pop     rdi
0x18002add4  pop     rsi
0x18002add5  pop     rbp
0x18002add6  retn
```
