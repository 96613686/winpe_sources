# CHttpRequest::Init(void *)

- ea: `0x18009ae70`
- end: `0x18009b027`
- name: `?Init@CHttpRequest@@QEAAJPEAX@Z`
- size: `439`
- prototype: `__int64 __fastcall(CHttpRequest *__hidden this, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800931dc`
- `0x1800a1ad0`

## callees

- `0x18000716c`
- `0x180007e34`
- `0x18001fe24`
- `0x18009ae70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009afad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009aebe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009af3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009afad`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009aea2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009af20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009af91`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009aea2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009af20`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009af91`

## pseudocode

```c
__int64 __fastcall CHttpRequest::Init(CHttpRequest *this, void *a2)
{
  _QWORD *v2; // r14
  HANDLE EventW; // rax
  DWORD LastError; // eax
  unsigned int v7; // ebx
  _QWORD *v8; // rdi
  HANDLE v9; // rax
  DWORD v10; // eax
  wchar_t *v11; // rcx
  __int64 v12; // rdx
  HANDLE v13; // rax
  DWORD v14; // eax

  v2 = (_QWORD *)((char *)this + 24);
  if ( (unsigned __int64)(*((_QWORD *)this + 3) + 1LL) <= 1 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(v2, EventW);
    if ( (unsigned __int64)(*v2 + 1LL) <= 1 )
    {
      LastError = GetLastError();
      v7 = ERROR_HR_FROM_WIN32(LastError);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v7);
      v8 = (_QWORD *)((char *)this + 32);
      goto LABEL_18;
    }
  }
  v8 = (_QWORD *)((char *)this + 32);
  if ( (unsigned __int64)(*((_QWORD *)this + 4) + 1LL) > 1
    || (v9 = CreateEventW(0, 1, 0, 0),
        tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 32, v9),
        (unsigned __int64)(*v8 + 1LL) > 1) )
  {
    if ( (unsigned __int64)(*((_QWORD *)this + 6) + 1LL) > 1
      || (v13 = CreateEventW(0, 1, 0, 0),
          tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 48, v13),
          (unsigned __int64)(*((_QWORD *)this + 6) + 1LL) > 1) )
    {
      *((_QWORD *)this + 5) = a2;
      return 0;
    }
    v14 = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(v14);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 12;
      goto LABEL_17;
    }
  }
  else
  {
    v10 = GetLastError();
    v7 = ERROR_HR_FROM_WIN32(v10);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v12 = 11;
LABEL_17:
      WPP_SF_d(*((_QWORD *)v11 + 2), v12, WPP_158c1c2611d1379e0dd259997317728c_Traceguids, v7);
    }
  }
LABEL_18:
  if ( (v7 & 0x80000000) != 0 )
  {
    tlx::unique_any<tlx::file_handle_traits>::reset(v2, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset(v8, 0);
    tlx::unique_any<tlx::file_handle_traits>::reset((char *)this + 48, 0);
  }
  return v7;
}

```

## disassembly

```asm
0x18009ae70  push    rbx
0x18009ae72  push    rbp
0x18009ae73  push    rsi
0x18009ae74  push    rdi
0x18009ae75  push    r14
0x18009ae77  push    r15
0x18009ae79  sub     rsp, 28h
0x18009ae7d  mov     r15d, 1
0x18009ae83  lea     r14, [rcx+18h]
0x18009ae87  mov     rax, [r14]
0x18009ae8a  mov     rbp, rdx
0x18009ae8d  add     rax, r15
0x18009ae90  mov     rsi, rcx
0x18009ae93  cmp     rax, r15
0x18009ae96  ja      short loc_18009AF06
0x18009ae98  xor     r9d, r9d; lpName
0x18009ae9b  xor     r8d, r8d; bInitialState
0x18009ae9e  xor     edx, edx; bManualReset
0x18009aea0  xor     ecx, ecx; lpEventAttributes
0x18009aea2  call    cs:__imp_CreateEventW
0x18009aea8  mov     rdx, rax
0x18009aeab  mov     rcx, r14
0x18009aeae  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009aeb3  mov     rax, [r14]
0x18009aeb6  add     rax, r15
0x18009aeb9  cmp     rax, r15
0x18009aebc  ja      short loc_18009AF06
0x18009aebe  call    cs:__imp_GetLastError
0x18009aec4  mov     ecx, eax; unsigned int
0x18009aec6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009aecb  mov     ebx, eax
0x18009aecd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009aed4  lea     rax, WPP_GLOBAL_Control
0x18009aedb  cmp     rcx, rax
0x18009aede  jz      short loc_18009AEFD
0x18009aee0  test    [rcx+1Ch], r15b
0x18009aee4  jz      short loc_18009AEFD
0x18009aee6  mov     rcx, [rcx+10h]
0x18009aeea  lea     edx, [r15+9]
0x18009aeee  mov     r9d, ebx
0x18009aef1  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009aef8  call    WPP_SF_d
0x18009aefd  lea     rdi, [rsi+20h]
0x18009af01  jmp     loc_18009AFED
0x18009af06  lea     rdi, [rsi+20h]
0x18009af0a  mov     rax, [rdi]
0x18009af0d  add     rax, r15
0x18009af10  cmp     rax, r15
0x18009af13  ja      short loc_18009AF73
0x18009af15  xor     r9d, r9d; lpName
0x18009af18  xor     r8d, r8d; bInitialState
0x18009af1b  mov     edx, r15d; bManualReset
0x18009af1e  xor     ecx, ecx; lpEventAttributes
0x18009af20  call    cs:__imp_CreateEventW
0x18009af26  mov     rdx, rax
0x18009af29  mov     rcx, rdi
0x18009af2c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009af31  mov     rax, [rdi]
0x18009af34  add     rax, r15
0x18009af37  cmp     rax, r15
0x18009af3a  ja      short loc_18009AF73
0x18009af3c  call    cs:__imp_GetLastError
0x18009af42  mov     ecx, eax; unsigned int
0x18009af44  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009af49  mov     ebx, eax
0x18009af4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18009af52  lea     rax, WPP_GLOBAL_Control
0x18009af59  cmp     rcx, rax
0x18009af5c  jz      loc_18009AFED
0x18009af62  test    [rcx+1Ch], r15b
0x18009af66  jz      loc_18009AFED
0x18009af6c  mov     edx, 0Bh
0x18009af71  jmp     short loc_18009AFDA
0x18009af73  lea     rbx, [rsi+30h]
0x18009af77  mov     rax, [rbx]
0x18009af7a  add     rax, r15
0x18009af7d  cmp     rax, r15
0x18009af80  ja      loc_18009B012
0x18009af86  xor     r9d, r9d; lpName
0x18009af89  xor     r8d, r8d; bInitialState
0x18009af8c  mov     edx, r15d; bManualReset
0x18009af8f  xor     ecx, ecx; lpEventAttributes
0x18009af91  call    cs:__imp_CreateEventW
0x18009af97  mov     rdx, rax
0x18009af9a  mov     rcx, rbx
0x18009af9d  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009afa2  mov     rax, [rbx]
0x18009afa5  add     rax, r15
0x18009afa8  cmp     rax, r15
0x18009afab  ja      short loc_18009B012
0x18009afad  call    cs:__imp_GetLastError
0x18009afb3  mov     ecx, eax; unsigned int
0x18009afb5  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18009afba  mov     ebx, eax
0x18009afbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18009afc3  lea     rax, WPP_GLOBAL_Control
0x18009afca  cmp     rcx, rax
0x18009afcd  jz      short loc_18009AFED
0x18009afcf  test    [rcx+1Ch], r15b
0x18009afd3  jz      short loc_18009AFED
0x18009afd5  mov     edx, 0Ch
0x18009afda  mov     rcx, [rcx+10h]
0x18009afde  lea     r8, WPP_158c1c2611d1379e0dd259997317728c_Traceguids
0x18009afe5  mov     r9d, ebx
0x18009afe8  call    WPP_SF_d
0x18009afed  test    ebx, ebx
0x18009afef  jns     short loc_18009B018
0x18009aff1  xor     edx, edx
0x18009aff3  mov     rcx, r14
0x18009aff6  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009affb  xor     edx, edx
0x18009affd  mov     rcx, rdi
0x18009b000  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009b005  lea     rcx, [rsi+30h]
0x18009b009  xor     edx, edx
0x18009b00b  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009b010  jmp     short loc_18009B018
0x18009b012  mov     [rsi+28h], rbp
0x18009b016  xor     ebx, ebx
0x18009b018  mov     eax, ebx
0x18009b01a  add     rsp, 28h
0x18009b01e  pop     r15
0x18009b020  pop     r14
0x18009b022  pop     rdi
0x18009b023  pop     rsi
0x18009b024  pop     rbp
0x18009b025  pop     rbx
0x18009b026  retn
```
