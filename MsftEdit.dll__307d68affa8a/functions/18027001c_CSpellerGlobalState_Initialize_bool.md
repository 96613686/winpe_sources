# CSpellerGlobalState::Initialize(bool)

- ea: `0x18027001c`
- end: `0x18027022a`
- name: `?Initialize@CSpellerGlobalState@@QEAAJ_N@Z`
- size: `526`
- prototype: `__int64 __fastcall(CSpellerGlobalState *__hidden this, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180112ed4`

## callees

- `0x180062788`
- `0x18010ba14`
- `0x1801136d0`
- `0x18013bad0`
- `0x18013beb8`
- `0x18013f2f0`
- `0x18027001c`
- `0x18027316c`
- `0x1802732bc`
- `0x18027791c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180270091`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180270091`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1802701b2`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x1802701b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180270078`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180270078`

## pseudocode

```c
__int64 __fastcall CSpellerGlobalState::Initialize(CSpellerGlobalState *this)
{
  int inited; // edi
  _DWORD *v3; // rax
  bool v4; // dl
  _QWORD *v5; // rax
  char v6; // cl
  _QWORD *v7; // rax
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-30h] BYREF

  if ( !IsSpellCheckFacilityPresent() )
    return (unsigned int)-2147467259;
  *((_BYTE *)this + 340) = (unsigned __int8)IsMappingGetServicesPresent() == 0;
  if ( WindowsCreateStringReference(L"Windows.Globalization.Language", 0x1Eu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  inited = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(
             string,
             (char *)this + 296);
  if ( inited >= 0 )
  {
    *((_DWORD *)this + 18) = CSpellerGlobalState::GetCurrentInputMethodLCID(this);
    v3 = operator new(0x18u);
    *(_QWORD *)v3 = 0;
    v3[2] = 8;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)this + 4) = v3;
    inited = CSpellerGlobalState::InitMultilingualResources(this, v4);
    if ( inited >= 0 )
    {
      inited = CSpellerGlobalState::AddNewInputMethod(this, *((_DWORD *)this + 18), 0);
      if ( inited >= 0 )
      {
        v5 = operator new(0xA8u);
        v6 = *((_BYTE *)this + 340);
        *v5 = 0;
        v5[1] = 0;
        v5[5] = 0;
        v5[6] = 0;
        v5[7] = 0;
        v5[18] = 0;
        *((_BYTE *)v5 + 158) = v6;
        v5[2] = 0;
        v5[3] = 0;
        *((_DWORD *)v5 + 38) = 0;
        *((_WORD *)v5 + 78) = 1;
        *((_BYTE *)v5 + 159) = 1;
        *((_DWORD *)v5 + 40) = 2;
        *(_QWORD *)((char *)v5 + 100) = 0;
        *(_QWORD *)((char *)v5 + 108) = 0;
        v5[8] = 0;
        v5[9] = 0;
        v5[10] = 0;
        v5[11] = 0;
        *((_DWORD *)v5 + 24) = 0;
        *(_QWORD *)((char *)v5 + 116) = 0;
        *(_QWORD *)((char *)v5 + 124) = 0;
        *(_QWORD *)((char *)v5 + 132) = 0;
        *((_QWORD *)this + 7) = v5;
        if ( *((_BYTE *)this + 66) )
        {
          (*(void (__fastcall **)(CSpellerGlobalState *))(*(_QWORD *)this + 8LL))(this);
          *((_DWORD *)this + 26) = 1;
          if ( !QueueUserWorkItem(CSpellerGlobalState::BackgroundInitializeThreadProc, this, 0) )
          {
            (*(void (__fastcall **)(CSpellerGlobalState *))(*(_QWORD *)this + 16LL))(this);
            *((_DWORD *)this + 26) = 2;
            return (unsigned int)-2147467259;
          }
        }
        else
        {
          inited = CSpellerGlobalState::ForegroundInitialize(this);
          if ( inited < 0 )
            return (unsigned int)inited;
        }
        v7 = operator new(0x30u);
        *v7 = 2;
        v7[1] = 0;
        v7[2] = 0;
        v7[3] = 0;
        v7[4] = 0;
        v7[5] = 0;
        *((_QWORD *)this + 10) = v7;
      }
    }
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18027001c  mov     [rsp+arg_8], rbx
0x180270021  mov     [rsp+arg_10], rsi
0x180270026  push    rdi
0x180270027  sub     rsp, 50h
0x18027002b  mov     rax, cs:__security_cookie
0x180270032  xor     rax, rsp
0x180270035  mov     [rsp+58h+var_18], rax
0x18027003a  mov     rbx, rcx
0x18027003d  call    ?IsSpellCheckFacilityPresent@@YA_NXZ; IsSpellCheckFacilityPresent(void)
0x180270042  xor     esi, esi
0x180270044  test    al, al
0x180270046  jnz     short loc_180270052
0x180270048  mov     edi, 80004005h
0x18027004d  jmp     loc_18027020B
0x180270052  call    IsMappingGetServicesPresent
0x180270057  test    al, al
0x180270059  lea     r9, [rsp+58h+string]; string
0x18027005e  lea     r8, [rsp+58h+hstringHeader]; hstringHeader
0x180270063  mov     edx, 1Eh; length
0x180270068  setz    al
0x18027006b  lea     rcx, ?RuntimeClass_Windows_Globalization_Language@@3QBGB; "Windows.Globalization.Language"
0x180270072  mov     [rbx+154h], al
0x180270078  call    cs:__imp_WindowsCreateStringReference
0x18027007e  test    eax, eax
0x180270080  jns     short loc_180270097
0x180270082  xor     r9d, r9d; lpArguments
0x180270085  xor     r8d, r8d; nNumberOfArguments
0x180270088  mov     ecx, 0C000000Dh; dwExceptionCode
0x18027008d  lea     edx, [r9+1]; dwExceptionFlags
0x180270091  call    cs:__imp_RaiseException
0x180270097  mov     rcx, [rsp+58h+string]
0x18027009c  lea     rdx, [rbx+128h]
0x1802700a3  call    ??$GetActivationFactory@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UILanguageStatics@Globalization@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Globalization::ILanguageStatics>>)
0x1802700a8  mov     edi, eax
0x1802700aa  test    eax, eax
0x1802700ac  js      loc_18027020B
0x1802700b2  mov     rcx, rbx; this
0x1802700b5  call    ?GetCurrentInputMethodLCID@CSpellerGlobalState@@QEBAKXZ; CSpellerGlobalState::GetCurrentInputMethodLCID(void)
0x1802700ba  mov     ecx, 18h; Size
0x1802700bf  mov     [rbx+48h], eax
0x1802700c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802700c7  mov     rcx, rbx; this
0x1802700ca  mov     [rax], rsi
0x1802700cd  mov     dword ptr [rax+8], 8
0x1802700d4  mov     [rax+10h], rsi
0x1802700d8  mov     [rbx+20h], rax
0x1802700dc  call    ?InitMultilingualResources@CSpellerGlobalState@@AEAAJ_N@Z; CSpellerGlobalState::InitMultilingualResources(bool)
0x1802700e1  mov     edi, eax
0x1802700e3  test    eax, eax
0x1802700e5  js      loc_18027020B
0x1802700eb  mov     edx, [rbx+48h]; unsigned int
0x1802700ee  xor     r8d, r8d; struct Microsoft::WRL::Wrappers::HString *
0x1802700f1  mov     rcx, rbx; this
0x1802700f4  call    ?AddNewInputMethod@CSpellerGlobalState@@QEAAJKPEAVHString@Wrappers@WRL@Microsoft@@@Z; CSpellerGlobalState::AddNewInputMethod(ulong,Microsoft::WRL::Wrappers::HString *)
0x1802700f9  mov     edi, eax
0x1802700fb  test    eax, eax
0x1802700fd  js      loc_18027020B
0x180270103  mov     ecx, 0A8h; Size
0x180270108  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18027010d  mov     cl, [rbx+154h]
0x180270113  mov     [rax], rsi
0x180270116  mov     [rax+8], rsi
0x18027011a  mov     [rax+28h], rsi
0x18027011e  mov     [rax+30h], rsi
0x180270122  mov     [rax+38h], rsi
0x180270126  mov     [rax+90h], rsi
0x18027012d  mov     [rax+9Eh], cl
0x180270133  mov     rcx, rbx; this
0x180270136  mov     [rax+10h], rsi
0x18027013a  mov     [rax+18h], rsi
0x18027013e  mov     [rax+98h], esi
0x180270144  mov     word ptr [rax+9Ch], 1
0x18027014d  mov     byte ptr [rax+9Fh], 1
0x180270154  mov     dword ptr [rax+0A0h], 2
0x18027015e  mov     [rax+64h], rsi
0x180270162  mov     [rax+6Ch], rsi
0x180270166  mov     [rax+40h], rsi
0x18027016a  mov     [rax+48h], rsi
0x18027016e  mov     [rax+50h], rsi
0x180270172  mov     [rax+58h], rsi
0x180270176  mov     [rax+60h], esi
0x180270179  mov     [rax+74h], rsi
0x18027017d  mov     [rax+7Ch], rsi
0x180270181  mov     [rax+84h], rsi
0x180270188  mov     [rbx+38h], rax
0x18027018c  cmp     [rbx+42h], sil
0x180270190  jz      short loc_1802701D7
0x180270192  mov     rax, [rbx]
0x180270195  mov     rax, [rax+8]
0x180270199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18027019e  xor     r8d, r8d; Flags
0x1802701a1  mov     dword ptr [rbx+68h], 1
0x1802701a8  mov     rdx, rbx; Context
0x1802701ab  lea     rcx, ?BackgroundInitializeThreadProc@CSpellerGlobalState@@CAKPEAX@Z; Function
0x1802701b2  call    cs:__imp_QueueUserWorkItem
0x1802701b8  test    eax, eax
0x1802701ba  jnz     short loc_1802701E2
0x1802701bc  mov     rax, [rbx]
0x1802701bf  mov     rcx, rbx
0x1802701c2  mov     rax, [rax+10h]
0x1802701c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802701cb  mov     dword ptr [rbx+68h], 2
0x1802701d2  jmp     loc_180270048
0x1802701d7  call    ?ForegroundInitialize@CSpellerGlobalState@@AEAAJXZ; CSpellerGlobalState::ForegroundInitialize(void)
0x1802701dc  mov     edi, eax
0x1802701de  test    eax, eax
0x1802701e0  js      short loc_18027020B
0x1802701e2  mov     ecx, 30h ; '0'; Size
0x1802701e7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802701ec  mov     qword ptr [rax], 2
0x1802701f3  mov     [rax+8], rsi
0x1802701f7  mov     [rax+10h], rsi
0x1802701fb  mov     [rax+18h], rsi
0x1802701ff  mov     [rax+20h], rsi
0x180270203  mov     [rax+28h], rsi
0x180270207  mov     [rbx+50h], rax
0x18027020b  mov     eax, edi
0x18027020d  mov     rcx, [rsp+58h+var_18]
0x180270212  xor     rcx, rsp; StackCookie
0x180270215  call    __security_check_cookie
0x18027021a  mov     rbx, [rsp+58h+arg_8]
0x18027021f  mov     rsi, [rsp+58h+arg_10]
0x180270224  add     rsp, 50h
0x180270228  pop     rdi
0x180270229  retn
```
