# Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::GetAudioModules(Windows::Foundation::Collections::IVector<Windows::Media::Devices::AudioDeviceModule *> *)

- ea: `0x1400163c0`
- end: `0x14001672b`
- name: `?GetAudioModules@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@UEAAJPEAU?$IVector@PEAVAudioDeviceModule@Devices@Media@Windows@@@Collections@Foundation@5@@Z`
- size: `875`
- prototype: `__int64 __fastcall(Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *this, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000c33c`
- `0x1400163c0`
- `0x140016734`
- `0x140023ab0`
- `0x14005e168`
- `0x140084fa0`
- `0x140088ac0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140016585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140016585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001656c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001661c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001662a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400166a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400166d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400166e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016521`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001656c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001661c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001662a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016667`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140016692`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400166a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400166d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400166e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001646f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14001646f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400166f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400166fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400166f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400166fc`

## pseudocode

```c
__int64 __fastcall Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::GetAudioModules(
        Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *this,
        __int64 a2)
{
  int v4; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int *v8; // rax
  unsigned int *v9; // rdi
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int *v13; // rbx
  unsigned int i; // esi
  HRESULT v15; // r14d
  int v16; // eax
  unsigned int v17; // r14d
  __int64 v18; // r14
  __int64 v19; // rdx
  int v20; // [rsp+20h] [rbp-49h]
  int v21; // [rsp+20h] [rbp-49h]
  UINT32 length[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v23; // [rsp+48h] [rbp-21h] BYREF
  HSTRING v24; // [rsp+50h] [rbp-19h] BYREF
  struct _GUID v25; // [rsp+60h] [rbp-9h] BYREF
  struct KSIDENTIFIER v26; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  SIZE_T cb; // [rsp+D8h] [rbp+6Fh] BYREF
  HSTRING string; // [rsp+E0h] [rbp+77h] BYREF
  HSTRING v30; // [rsp+E8h] [rbp+7Fh] BYREF

  LODWORD(cb) = 0;
  if ( a2 )
  {
    v26.Set = GUID_c034fdb0_ff75_47c8_aa3c_ee46716b50c6;
    *(&v26.Alignment + 2) = 0x100000001LL;
    v4 = Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(
           this,
           &v26,
           0x20u,
           0,
           0,
           (unsigned int *)&cb);
    if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147024662 || !(_DWORD)cb )
      return 0;
    v8 = (unsigned int *)CoTaskMemAlloc((unsigned int)cb);
    v9 = v8;
    if ( v8 )
    {
      memset_0(v8, 0, (unsigned int)cb);
      v10 = Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(
              this,
              &v26,
              0x20u,
              v9,
              cb,
              (unsigned int *)&cb);
      v6 = v10;
      if ( v10 < 0 )
      {
        v11 = (unsigned int)v10;
        v12 = 2466;
        goto LABEL_14;
      }
      if ( (unsigned int)cb < 8 )
      {
        v12 = 2469;
LABEL_13:
        v6 = -2147418113;
        v11 = 2147549183LL;
LABEL_14:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
          (const char *)v11,
          v21);
LABEL_29:
        CoTaskMemFree(v9);
        return v6;
      }
      if ( (unsigned int)cb < 8 * (unsigned __int64)v9[1] + 8 )
      {
        v12 = 2471;
        goto LABEL_13;
      }
      v13 = v9 + 2;
      for ( i = 0; i < v9[1]; ++i )
      {
        v30 = 0;
        string = 0;
        *(_QWORD *)length = 0;
        WindowsDeleteString(0);
        v30 = 0;
        v25 = *(struct _GUID *)v13;
        v15 = GuidToHString(&v25, &v30);
        if ( v15 < 0 )
        {
          v19 = 2481;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
            (const char *)(unsigned int)v15,
            v21);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v30);
          v6 = v15;
LABEL_28:
          v30 = 0;
          goto LABEL_29;
        }
        v16 = StringCchLengthW((const unsigned __int16 *)v13 + 14, 0x80u, (unsigned __int64 *)length);
        v17 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9B2,
            (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
            (const char *)(unsigned int)v16,
            v21);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v30);
          v30 = 0;
          v6 = v17;
          goto LABEL_29;
        }
        WindowsDeleteString(string);
        string = 0;
        v15 = WindowsCreateString((PCNZWCH)v13 + 14, length[0], &string);
        if ( v15 < 0 )
        {
          v19 = 2483;
          goto LABEL_27;
        }
        *(_QWORD *)length = this;
        v24 = string;
        *(_QWORD *)&v25.Data1 = v30;
        Microsoft::WRL::Details::Make<Windows::Media::Devices::AudioDeviceModule,HSTRING__ *,unsigned long &,HSTRING__ *,unsigned long &,unsigned long &,Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>(
          (unsigned int)&v23,
          (unsigned int)&v25,
          (_DWORD)v13 + 16,
          (unsigned int)&v24,
          (__int64)(v13 + 5),
          (__int64)(v13 + 6),
          (__int64)length);
        v18 = v23;
        if ( !v23 )
        {
          v6 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9BB,
            (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
            (const char *)0x8007000ELL,
            v21);
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v30);
          goto LABEL_28;
        }
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a2 + 104LL))(a2, v23);
        v13 += 71;
        v23 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v30);
      }
      CoTaskMemFree(v9);
      return 0;
    }
    v6 = -2147024882;
    v7 = 2458;
  }
  else
  {
    v6 = -2147024809;
    v7 = 2429;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v7,
    (unsigned int)"avcore\\audiocore\\deviceapi\\device\\lib\\audiodevicemodule.cpp",
    (const char *)v6,
    v20);
  return v6;
}

```

## disassembly

```asm
0x1400163c0  mov     [rsp-8+arg_0], rbx
0x1400163c5  push    rbp
0x1400163c6  push    rsi
0x1400163c7  push    rdi
0x1400163c8  push    r12
0x1400163ca  push    r13
0x1400163cc  push    r14
0x1400163ce  push    r15
0x1400163d0  lea     rbp, [rsp-27h]
0x1400163d5  sub     rsp, 90h
0x1400163dc  mov     r15, rdx
0x1400163df  mov     r13, rcx
0x1400163e2  xor     r12d, r12d
0x1400163e5  mov     dword ptr [rbp+57h+cb], r12d
0x1400163e9  test    rdx, rdx
0x1400163ec  jz      short loc_140016457
0x1400163ee  movups  xmm0, xmmword ptr cs:_GUID_c034fdb0_ff75_47c8_aa3c_ee46716b50c6.Data1
0x1400163f5  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x1400163fa  lea     eax, [r12+1]
0x1400163ff  mov     dword ptr [rbp+57h+var_50+10h], eax
0x140016402  mov     dword ptr [rbp+57h+var_50+14h], eax
0x140016405  lea     rax, [rbp+57h+cb]
0x140016409  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x14001640e  mov     [rsp+0C0h+var_A0], r12d; int
0x140016413  xor     r9d, r9d; void *
0x140016416  lea     ebx, [r12+20h]
0x14001641b  mov     r8d, ebx; unsigned int
0x14001641e  lea     rdx, [rbp+57h+var_50]; struct KSIDENTIFIER *
0x140016422  call    ?KsSendProperty@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@AEAAJPEAUKSIDENTIFIER@@KPEAXIPEAK@Z; Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(KSIDENTIFIER *,ulong,void *,uint,ulong *)
0x140016427  mov     edx, 80000000h
0x14001642c  lea     ecx, [rax+rdx]
0x14001642f  test    edx, ecx
0x140016431  jnz     short loc_140016466
0x140016433  cmp     eax, 800700EAh
0x140016438  jz      short loc_140016466
0x14001643a  xor     eax, eax
0x14001643c  mov     rbx, [rsp+0C0h+arg_0]
0x140016444  add     rsp, 90h
0x14001644b  pop     r15
0x14001644d  pop     r14
0x14001644f  pop     r13
0x140016451  pop     r12
0x140016453  pop     rdi
0x140016454  pop     rsi
0x140016455  pop     rbp
0x140016456  retn
0x140016457  mov     ebx, 80070057h
0x14001645c  mov     edx, 97Dh
0x140016461  jmp     loc_140016711
0x140016466  mov     eax, dword ptr [rbp+57h+cb]
0x140016469  test    eax, eax
0x14001646b  jz      short loc_14001643A
0x14001646d  mov     ecx, eax; cb
0x14001646f  call    cs:__imp_CoTaskMemAlloc
0x140016475  mov     rdi, rax
0x140016478  test    rax, rax
0x14001647b  jz      loc_140016707
0x140016481  mov     r8d, dword ptr [rbp+57h+cb]; Size
0x140016485  xor     edx, edx; Val
0x140016487  mov     rcx, rax; void *
0x14001648a  call    memset_0
0x14001648f  mov     ecx, dword ptr [rbp+57h+cb]
0x140016492  lea     rax, [rbp+57h+cb]
0x140016496  mov     [rsp+0C0h+var_98], rax; unsigned int *
0x14001649b  mov     [rsp+0C0h+var_A0], ecx; int
0x14001649f  mov     r9, rdi; void *
0x1400164a2  mov     r8d, ebx; unsigned int
0x1400164a5  lea     rdx, [rbp+57h+var_50]; struct KSIDENTIFIER *
0x1400164a9  mov     rcx, r13; this
0x1400164ac  call    ?KsSendProperty@AudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@AEAAJPEAUKSIDENTIFIER@@KPEAXIPEAK@Z; Windows::Media::Devices::Internal::AudioDeviceBrokerDevice::KsSendProperty(KSIDENTIFIER *,ulong,void *,uint,ulong *)
0x1400164b1  mov     ebx, eax
0x1400164b3  test    eax, eax
0x1400164b5  jns     short loc_1400164C1
0x1400164b7  mov     r9d, eax
0x1400164ba  mov     edx, 9A2h
0x1400164bf  jmp     short loc_1400164DB
0x1400164c1  cmp     dword ptr [rbp+57h+cb], 8
0x1400164c5  jnb     short loc_1400164F0
0x1400164c7  mov     edx, 9A5h
0x1400164cc  jmp     short loc_1400164D3
0x1400164ce  mov     edx, 9A7h; void *
0x1400164d3  mov     ebx, 8000FFFFh
0x1400164d8  mov     r9d, ebx; char *
0x1400164db  mov     rcx, [rbp+5Fh]; this
0x1400164df  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x1400164e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400164eb  jmp     loc_1400166EE
0x1400164f0  mov     eax, [rdi+4]
0x1400164f3  lea     rcx, ds:8[rax*8]
0x1400164fb  mov     eax, dword ptr [rbp+57h+cb]
0x1400164fe  cmp     rax, rcx
0x140016501  jb      short loc_1400164CE
0x140016503  lea     rbx, [rdi+8]
0x140016507  mov     esi, r12d
0x14001650a  cmp     esi, [rdi+4]
0x14001650d  jnb     loc_1400166F9
0x140016513  mov     [rbp+57h+arg_18], r12
0x140016517  mov     [rbp+57h+string], r12
0x14001651b  mov     qword ptr [rbp+57h+length], r12
0x14001651f  xor     ecx, ecx; string
0x140016521  call    cs:__imp_WindowsDeleteString
0x140016527  mov     [rbp+57h+arg_18], r12
0x14001652b  movups  xmm0, xmmword ptr [rbx]
0x14001652e  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x140016533  lea     rdx, [rbp+57h+arg_18]; HSTRING *
0x140016537  lea     rcx, [rbp+57h+var_60]; struct _GUID
0x14001653b  call    ?GuidToHString@@YAJU_GUID@@PEAPEAUHSTRING__@@@Z; GuidToHString(_GUID,HSTRING__ * *)
0x140016540  mov     r14d, eax
0x140016543  test    eax, eax
0x140016545  js      loc_1400166B7
0x14001654b  lea     r8, [rbp+57h+length]; unsigned __int64 *
0x14001654f  mov     edx, 80h; unsigned __int64
0x140016554  lea     rcx, [rbx+1Ch]; unsigned __int16 *
0x140016558  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14001655d  mov     r14d, eax
0x140016560  test    eax, eax
0x140016562  js      loc_140016676
0x140016568  mov     rcx, [rbp+57h+string]; string
0x14001656c  call    cs:__imp_WindowsDeleteString
0x140016572  mov     [rbp+57h+string], 0
0x14001657a  lea     r8, [rbp+57h+string]; string
0x14001657e  mov     edx, [rbp+57h+length]; length
0x140016581  lea     rcx, [rbx+1Ch]; sourceString
0x140016585  call    cs:__imp_WindowsCreateString
0x14001658b  mov     r14d, eax
0x14001658e  xor     r12d, r12d
0x140016591  test    eax, eax
0x140016593  js      loc_14001666F
0x140016599  mov     qword ptr [rbp+57h+length], r13
0x14001659d  mov     rax, [rbp+57h+string]
0x1400165a1  mov     [rbp+57h+var_70], rax
0x1400165a5  mov     rax, [rbp+57h+arg_18]
0x1400165a9  mov     qword ptr [rbp+57h+var_60.Data1], rax
0x1400165ad  lea     rax, [rbx+18h]
0x1400165b1  lea     rcx, [rbx+14h]
0x1400165b5  lea     r8, [rbx+10h]
0x1400165b9  lea     rdx, [rbp+57h+length]
0x1400165bd  mov     [rsp+0C0h+var_90], rdx
0x1400165c2  mov     [rsp+0C0h+var_98], rax
0x1400165c7  mov     qword ptr [rsp+0C0h+var_A0], rcx; int
0x1400165cc  lea     r9, [rbp+57h+var_70]
0x1400165d0  lea     rdx, [rbp+57h+var_60]
0x1400165d4  lea     rcx, [rbp+57h+var_78]
0x1400165d8  call    ??$Make@VAudioDeviceModule@Devices@Media@Windows@@PEAUHSTRING__@@AEAKPEAU5@AEAKAEAKPEAVAudioDeviceBrokerDevice@Internal@234@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAudioDeviceModule@Devices@Media@Windows@@@12@$$QEAPEAUHSTRING__@@AEAK011$$QEAPEAVAudioDeviceBrokerDevice@Internal@Devices@Media@Windows@@@Z; Microsoft::WRL::Details::Make<Windows::Media::Devices::AudioDeviceModule,HSTRING__ *,ulong &,HSTRING__ *,ulong &,ulong &,Windows::Media::Devices::Internal::AudioDeviceBrokerDevice *>(HSTRING__ * &&,ulong &,HSTRING__ * &&,ulong &,ulong &,Windows::Media::Devices::Internal::AudioDeviceBrokerDevice * &&)
0x1400165dd  mov     r14, [rbp+57h+var_78]
0x1400165e1  test    r14, r14
0x1400165e4  jz      short loc_140016637
0x1400165e6  mov     rax, [r15]
0x1400165e9  mov     rdx, r14
0x1400165ec  mov     rcx, r15
0x1400165ef  mov     rax, [rax+68h]
0x1400165f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400165f8  add     rbx, 11Ch
0x1400165ff  test    r14, r14
0x140016602  jz      short loc_140016618
0x140016604  mov     [rbp+57h+var_78], r12
0x140016608  mov     rax, [r14]
0x14001660b  mov     rcx, r14
0x14001660e  mov     rax, [rax+10h]
0x140016612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016617  nop
0x140016618  mov     rcx, [rbp+57h+string]; string
0x14001661c  call    cs:__imp_WindowsDeleteString
0x140016622  mov     [rbp+57h+string], r12
0x140016626  mov     rcx, [rbp+57h+arg_18]; string
0x14001662a  call    cs:__imp_WindowsDeleteString
0x140016630  inc     esi
0x140016632  jmp     loc_14001650A
0x140016637  mov     rcx, [rbp+5Fh]; this
0x14001663b  mov     ebx, 8007000Eh
0x140016640  mov     r9d, ebx; char *
0x140016643  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14001664a  mov     edx, 9BBh; void *
0x14001664f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016654  nop
0x140016655  mov     rcx, [rbp+57h+string]; string
0x140016659  call    cs:__imp_WindowsDeleteString
0x14001665f  mov     [rbp+57h+string], r12
0x140016663  mov     rcx, [rbp+57h+arg_18]; string
0x140016667  call    cs:__imp_WindowsDeleteString
0x14001666d  jmp     short loc_1400166EA
0x14001666f  mov     edx, 9B3h
0x140016674  jmp     short loc_1400166BC
0x140016676  mov     rcx, [rbp+5Fh]; this
0x14001667a  mov     r9d, r14d; char *
0x14001667d  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x140016684  mov     edx, 9B2h; void *
0x140016689  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001668e  mov     rcx, [rbp+57h+string]; string
0x140016692  call    cs:__imp_WindowsDeleteString
0x140016698  mov     [rbp+57h+string], 0
0x1400166a0  mov     rcx, [rbp+57h+arg_18]; string
0x1400166a4  call    cs:__imp_WindowsDeleteString
0x1400166aa  mov     [rbp+57h+arg_18], 0
0x1400166b2  mov     ebx, r14d
0x1400166b5  jmp     short loc_1400166EE
0x1400166b7  mov     edx, 9B1h; void *
0x1400166bc  mov     r9d, r14d; char *
0x1400166bf  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x1400166c6  mov     rcx, [rbp+5Fh]; this
0x1400166ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400166cf  mov     rcx, [rbp+57h+string]; string
0x1400166d3  call    cs:__imp_WindowsDeleteString
0x1400166d9  mov     [rbp+57h+string], r12
0x1400166dd  mov     rcx, [rbp+57h+arg_18]; string
0x1400166e1  call    cs:__imp_WindowsDeleteString
0x1400166e7  mov     ebx, r14d
0x1400166ea  mov     [rbp+57h+arg_18], r12
0x1400166ee  mov     rcx, rdi; pv
0x1400166f1  call    cs:__imp_CoTaskMemFree
0x1400166f7  jmp     short loc_140016724
0x1400166f9  mov     rcx, rdi; pv
0x1400166fc  call    cs:__imp_CoTaskMemFree
0x140016702  jmp     loc_14001643A
0x140016707  mov     ebx, 8007000Eh
0x14001670c  mov     edx, 99Ah; void *
0x140016711  mov     r9d, ebx; char *
0x140016714  lea     r8, aAvcoreAudiocor_20; "avcore\\audiocore\\deviceapi\\device\\l"...
0x14001671b  mov     rcx, [rbp+5Fh]; this
0x14001671f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016724  mov     eax, ebx
0x140016726  jmp     loc_14001643C
```
