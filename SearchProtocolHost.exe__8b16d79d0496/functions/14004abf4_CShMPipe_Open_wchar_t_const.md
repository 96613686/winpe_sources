# CShMPipe::Open(wchar_t const *)

- ea: `0x14004abf4`
- end: `0x14004ae97`
- name: `?Open@CShMPipe@@QEAAJPEB_W@Z`
- size: `675`
- prototype: `__int64 __fastcall(CShMPipe *this, const wchar_t *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`
- `0x14003a8e8`

## callees

- `0x140005240`
- `0x14000ca80`
- `0x14000e97c`
- `0x1400104c8`
- `0x140012394`
- `0x14001d1d8`
- `0x14002801c`
- `0x140037ca8`
- `0x14004abf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004ade9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004ae3c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004ade9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14004ae3c`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004ace4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004ad34`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004ad99`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004ace4`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004ad34`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x14004ad99`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14004ac3b`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x14004ac3b`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14004ac88`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x14004ac88`

## string_xrefs

- `0x14004ac9b`: `onecoreuap\base\appmodel\search\common\pkmutild\shmpipe.cxx`
- `0x14004ad5e`: `onecoreuap\base\appmodel\search\common\pkmutild\shmpipe.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CShMPipe::Open(CShMPipe *this, const wchar_t *a2)
{
  HANDLE *v4; // rbx
  HANDLE v5; // rax
  wil::details *v6; // rcx
  LPVOID v8; // rax
  const char *v9; // r9
  HANDLE v10; // rax
  const char *v11; // r9
  __int64 v12; // rdx
  HANDLE v13; // rax
  unsigned int LastError; // ebx
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  _BYTE v18[8]; // [rsp+48h] [rbp-39h] BYREF
  LPCWSTR lpName; // [rsp+50h] [rbp-31h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v4 = (HANDLE *)((char *)this + 72);
  v5 = OpenFileMappingW(0xF001Fu, 0, a2);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    v4,
    v5);
  if ( (((unsigned __int64)*v4 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    return wil::details::GetLastErrorFailHr(v6);
  CLMString::operator=((char *)this + 152, a2);
  v8 = MapViewOfFile(*v4, 0xF001Fu, 0, 0, 0x10000u);
  *((_QWORD *)this + 10) = v8;
  if ( !v8 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1D9,
             (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
             v9);
  TLMString<32,32,1024>::TLMString<32,32,1024>(v18, a2);
  CLMString::Append((CLMString *)v18, L"DRE", 0xFFFFFFFF);
  v10 = OpenEventW(0x1F0003u, 0, lpName);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 88,
    v10);
  if ( ((*((_QWORD *)this + 11) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    CLMString::operator=(v18, a2);
    CLMString::Append((CLMString *)v18, L"DAE", 0xFFFFFFFF);
    v13 = OpenEventW(0x1F0003u, 0, lpName);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 96,
      v13);
    if ( ((*((_QWORD *)this + 12) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    {
      CLMString::operator=(v18, a2);
      CLMString::Append((CLMString *)v18, L"DSE", 0xFFFFFFFF);
      v15 = OpenEventW(0x1F0003u, 0, lpName);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 104,
        v15);
      if ( ((*((_QWORD *)this + 13) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        CLMString::operator=(v18, a2);
        CLMString::Append((CLMString *)v18, L"TRM", 0xFFFFFFFF);
        v16 = OpenSemaphoreW(0x1F0003u, 0, lpName);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 112,
          v16);
        if ( ((*((_QWORD *)this + 14) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        {
          CLMString::operator=(v18, a2);
          CLMString::Append((CLMString *)v18, L"RCM", 0xFFFFFFFF);
          v17 = OpenSemaphoreW(0x1F0003u, 0, lpName);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            (char *)this + 120,
            v17);
          if ( ((*((_QWORD *)this + 15) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
          {
            LastError = 0;
            goto LABEL_17;
          }
          v12 = 504;
        }
        else
        {
          v12 = 498;
        }
      }
      else
      {
        v12 = 492;
      }
    }
    else
    {
      v12 = 486;
    }
  }
  else
  {
    v12 = 480;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v12,
                (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\shmpipe.cxx",
                v11);
LABEL_17:
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v18);
  return LastError;
}

```

## disassembly

```asm
0x14004abf4  mov     rax, rsp
0x14004abf7  push    rbp
0x14004abf8  push    rsi
0x14004abf9  push    rdi
0x14004abfa  push    r14
0x14004abfc  push    r15
0x14004abfe  lea     rbp, [rax-5Fh]
0x14004ac02  sub     rsp, 0B0h
0x14004ac09  mov     [rbp+57h+var_A0], 0FFFFFFFFFFFFFFFEh
0x14004ac11  mov     [rax+18h], rbx
0x14004ac15  mov     rax, cs:__security_cookie
0x14004ac1c  xor     rax, rsp
0x14004ac1f  mov     [rbp+57h+var_30], rax
0x14004ac23  mov     rsi, rdx
0x14004ac26  mov     rdi, rcx
0x14004ac29  lea     rbx, [rcx+48h]
0x14004ac2d  mov     r8, rdx; lpName
0x14004ac30  xor     edx, edx; bInheritHandle
0x14004ac32  mov     r14d, 0F001Fh
0x14004ac38  mov     ecx, r14d; dwDesiredAccess
0x14004ac3b  call    cs:__imp_OpenFileMappingW
0x14004ac41  mov     rdx, rax
0x14004ac44  mov     rcx, rbx
0x14004ac47  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004ac4c  mov     rax, [rbx]
0x14004ac4f  inc     rax
0x14004ac52  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004ac58  jnz     short loc_14004AC64
0x14004ac5a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14004ac5f  jmp     loc_14004AE74
0x14004ac64  lea     rcx, [rdi+98h]
0x14004ac6b  mov     rdx, rsi
0x14004ac6e  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004ac73  mov     qword ptr [rsp+20h], 10000h; dwNumberOfBytesToMap
0x14004ac7c  xor     r9d, r9d; dwFileOffsetLow
0x14004ac7f  xor     r8d, r8d; dwFileOffsetHigh
0x14004ac82  mov     edx, r14d; dwDesiredAccess
0x14004ac85  mov     rcx, [rbx]; hFileMappingObject
0x14004ac88  call    cs:__imp_MapViewOfFile
0x14004ac8e  mov     [rdi+50h], rax
0x14004ac92  test    rax, rax
0x14004ac95  jnz     short loc_14004ACB1
0x14004ac97  mov     rcx, [rbp+5Fh]; this
0x14004ac9b  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004aca2  mov     edx, 1D9h; void *
0x14004aca7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14004acac  jmp     loc_14004AE74
0x14004acb1  mov     rdx, rsi
0x14004acb4  lea     rcx, [rbp+57h+var_90]
0x14004acb8  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x14004acbd  nop
0x14004acbe  or      r14d, 0FFFFFFFFh
0x14004acc2  mov     r8d, r14d; unsigned int
0x14004acc5  lea     rdx, aDre; "DRE"
0x14004accc  lea     rcx, [rbp+57h+var_90]; this
0x14004acd0  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x14004acd5  mov     r8, [rbp+57h+lpName]; lpName
0x14004acd9  xor     edx, edx; bInheritHandle
0x14004acdb  mov     r15d, 1F0003h
0x14004ace1  mov     ecx, r15d; dwDesiredAccess
0x14004ace4  call    cs:__imp_OpenEventW
0x14004acea  mov     rdx, rax
0x14004aced  lea     rcx, [rdi+58h]
0x14004acf1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004acf6  mov     rax, [rdi+58h]
0x14004acfa  inc     rax
0x14004acfd  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004ad03  jnz     short loc_14004AD0C
0x14004ad05  mov     edx, 1E0h
0x14004ad0a  jmp     short loc_14004AD5A
0x14004ad0c  mov     rdx, rsi
0x14004ad0f  lea     rcx, [rbp+57h+var_90]
0x14004ad13  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004ad18  mov     r8d, r14d; unsigned int
0x14004ad1b  lea     rdx, aDae; "DAE"
0x14004ad22  lea     rcx, [rbp+57h+var_90]; this
0x14004ad26  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x14004ad2b  mov     r8, [rbp+57h+lpName]; lpName
0x14004ad2f  xor     edx, edx; bInheritHandle
0x14004ad31  mov     ecx, r15d; dwDesiredAccess
0x14004ad34  call    cs:__imp_OpenEventW
0x14004ad3a  mov     rdx, rax
0x14004ad3d  lea     rcx, [rdi+60h]
0x14004ad41  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004ad46  mov     rax, [rdi+60h]
0x14004ad4a  inc     rax
0x14004ad4d  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004ad53  jnz     short loc_14004AD71
0x14004ad55  mov     edx, 1E6h; void *
0x14004ad5a  mov     rcx, [rbp+5Fh]; this
0x14004ad5e  lea     r8, aOnecoreuapBase_23; "onecoreuap\\base\\appmodel\\search\\com"...
0x14004ad65  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14004ad6a  mov     ebx, eax
0x14004ad6c  jmp     loc_14004AE69
0x14004ad71  mov     rdx, rsi
0x14004ad74  lea     rcx, [rbp+57h+var_90]
0x14004ad78  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004ad7d  mov     r8d, r14d; unsigned int
0x14004ad80  lea     rdx, aDse; "DSE"
0x14004ad87  lea     rcx, [rbp+57h+var_90]; this
0x14004ad8b  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x14004ad90  mov     r8, [rbp+57h+lpName]; lpName
0x14004ad94  xor     edx, edx; bInheritHandle
0x14004ad96  mov     ecx, r15d; dwDesiredAccess
0x14004ad99  call    cs:__imp_OpenEventW
0x14004ad9f  mov     rdx, rax
0x14004ada2  lea     rcx, [rdi+68h]
0x14004ada6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004adab  mov     rax, [rdi+68h]
0x14004adaf  inc     rax
0x14004adb2  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004adb8  jnz     short loc_14004ADC1
0x14004adba  mov     edx, 1ECh
0x14004adbf  jmp     short loc_14004AD5A
0x14004adc1  mov     rdx, rsi
0x14004adc4  lea     rcx, [rbp+57h+var_90]
0x14004adc8  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004adcd  mov     r8d, r14d; unsigned int
0x14004add0  lea     rdx, aTrm; "TRM"
0x14004add7  lea     rcx, [rbp+57h+var_90]; this
0x14004addb  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x14004ade0  mov     r8, [rbp+57h+lpName]; lpName
0x14004ade4  xor     edx, edx; bInheritHandle
0x14004ade6  mov     ecx, r15d; dwDesiredAccess
0x14004ade9  call    cs:__imp_OpenSemaphoreW
0x14004adef  mov     rdx, rax
0x14004adf2  lea     rcx, [rdi+70h]
0x14004adf6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004adfb  mov     rax, [rdi+70h]
0x14004adff  inc     rax
0x14004ae02  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004ae08  jnz     short loc_14004AE14
0x14004ae0a  mov     edx, 1F2h
0x14004ae0f  jmp     loc_14004AD5A
0x14004ae14  mov     rdx, rsi
0x14004ae17  lea     rcx, [rbp+57h+var_90]
0x14004ae1b  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x14004ae20  mov     r8d, r14d; unsigned int
0x14004ae23  lea     rdx, aRcm; "RCM"
0x14004ae2a  lea     rcx, [rbp+57h+var_90]; this
0x14004ae2e  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x14004ae33  mov     r8, [rbp+57h+lpName]; lpName
0x14004ae37  xor     edx, edx; bInheritHandle
0x14004ae39  mov     ecx, r15d; dwDesiredAccess
0x14004ae3c  call    cs:__imp_OpenSemaphoreW
0x14004ae42  mov     rdx, rax
0x14004ae45  lea     rcx, [rdi+78h]
0x14004ae49  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14004ae4e  mov     rax, [rdi+78h]
0x14004ae52  inc     rax
0x14004ae55  test    rax, 0FFFFFFFFFFFFFFFEh
0x14004ae5b  jnz     short loc_14004AE67
0x14004ae5d  mov     edx, 1F8h
0x14004ae62  jmp     loc_14004AD5A
0x14004ae67  xor     ebx, ebx
0x14004ae69  lea     rcx, [rbp+57h+var_90]
0x14004ae6d  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x14004ae72  mov     eax, ebx
0x14004ae74  mov     rcx, [rbp+57h+var_30]
0x14004ae78  xor     rcx, rsp; StackCookie
0x14004ae7b  call    __security_check_cookie
0x14004ae80  mov     rbx, [rsp+0D0h+arg_10]
0x14004ae88  add     rsp, 0B0h
0x14004ae8f  pop     r15
0x14004ae91  pop     r14
0x14004ae93  pop     rdi
0x14004ae94  pop     rsi
0x14004ae95  pop     rbp
0x14004ae96  retn
```
