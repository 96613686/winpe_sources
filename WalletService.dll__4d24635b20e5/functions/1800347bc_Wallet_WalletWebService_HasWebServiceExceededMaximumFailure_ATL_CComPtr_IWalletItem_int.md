# Wallet::WalletWebService::HasWebServiceExceededMaximumFailure(ATL::CComPtr<IWalletItem> &,int *)

- ea: `0x1800347bc`
- end: `0x180034911`
- name: `?HasWebServiceExceededMaximumFailure@WalletWebService@Wallet@@QEAAJAEAV?$CComPtr@UIWalletItem@@@ATL@@PEAH@Z`
- size: `341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800342a8`
- `0x180034c48`

## callees

- `0x1800347bc`
- `0x180036b60`
- `0x180036bdc`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034874`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034874`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003485c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18003485c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800348db`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800348db`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003486a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18003486a`

## pseudocode

```c
__int64 __fastcall Wallet::WalletWebService::HasWebServiceExceededMaximumFailure(__int64 a1, _QWORD *a2, BOOL *a3)
{
  __int64 v6; // rcx
  unsigned int TInt; // eax
  unsigned int TFileTime; // ebx
  signed int LastError; // eax
  BOOL v10; // eax
  FILETIME FileTime1; // [rsp+20h] [rbp-40h] BYREF
  int v13; // [rsp+28h] [rbp-38h] BYREF
  FILETIME v14; // [rsp+30h] [rbp-30h]
  struct _FILETIME FileTime; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-20h] BYREF

  v13 = 0;
  FileTime1 = 0;
  FileTime = 0;
  v6 = *a2;
  SystemTime = 0;
  TInt = Wallet::Utils::GetTIntProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(v6, 160, &v13);
  TFileTime = TInt;
  if ( (int)(TInt + 0x80000000) < 0 || TInt == -2143682560 )
  {
    TFileTime = Wallet::Utils::GetTFileTimeProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                  *a2,
                  161,
                  &FileTime1);
    if ( ((TFileTime + 0x80000000) & 0x80000000) != 0 || TFileTime == -2143682560 )
    {
      GetSystemTime(&SystemTime);
      if ( SystemTimeToFileTime(&SystemTime, &FileTime) )
      {
        TFileTime = 0;
        v14 = (FILETIME)(864000000000LL * *(unsigned int *)(a1 + 120) + *(_QWORD *)&FileTime1);
        FileTime1 = v14;
        v10 = v13 >= *(_DWORD *)(a1 + 116) && CompareFileTime(&FileTime1, &FileTime) <= 0;
        *a3 = v10;
      }
      else
      {
        LastError = GetLastError();
        TFileTime = LastError;
        if ( LastError )
        {
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
        else
        {
          return (unsigned int)-2143748092;
        }
      }
    }
  }
  return TFileTime;
}

```

## disassembly

```asm
0x1800347bc  mov     [rsp-28h+arg_18], rbx
0x1800347c1  push    rbp
0x1800347c2  push    rsi
0x1800347c3  push    rdi
0x1800347c4  push    r13
0x1800347c6  push    r14
0x1800347c8  mov     rbp, rsp
0x1800347cb  sub     rsp, 60h
0x1800347cf  mov     rax, cs:__security_cookie
0x1800347d6  xor     rax, rsp
0x1800347d9  mov     [rbp+var_10], rax
0x1800347dd  mov     rsi, rdx
0x1800347e0  mov     [rbp+var_38], 0
0x1800347e7  mov     r14, r8
0x1800347ea  mov     qword ptr [rbp+FileTime1.dwLowDateTime], 0
0x1800347f2  mov     rdi, rcx
0x1800347f5  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x1800347fd  xorps   xmm0, xmm0
0x180034800  lea     r8, [rbp+var_38]
0x180034804  mov     rcx, [rsi]
0x180034807  mov     edx, 0A0h
0x18003480c  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x180034810  call    ??$GetTIntProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAH@Z; Wallet::Utils::GetTIntProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,int *)
0x180034815  mov     r13d, 80000000h
0x18003481b  mov     ebx, eax
0x18003481d  lea     edx, [rax+r13]
0x180034821  test    r13d, edx
0x180034824  jnz     short loc_180034831
0x180034826  cmp     eax, 803A0000h
0x18003482b  jnz     loc_1800348EF
0x180034831  mov     rcx, [rsi]
0x180034834  lea     r8, [rbp+FileTime1]
0x180034838  mov     edx, 0A1h
0x18003483d  call    ??$GetTFileTimeProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAU_FILETIME@@@Z; Wallet::Utils::GetTFileTimeProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,_FILETIME *)
0x180034842  mov     ebx, eax
0x180034844  add     eax, r13d
0x180034847  test    r13d, eax
0x18003484a  jnz     short loc_180034858
0x18003484c  cmp     ebx, 803A0000h
0x180034852  jnz     loc_1800348EF
0x180034858  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18003485c  call    cs:__imp_GetSystemTime
0x180034862  lea     rdx, [rbp+FileTime]; lpFileTime
0x180034866  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18003486a  call    cs:__imp_SystemTimeToFileTime
0x180034870  test    eax, eax
0x180034872  jnz     short loc_180034894
0x180034874  call    cs:__imp_GetLastError
0x18003487a  mov     ebx, eax
0x18003487c  test    eax, eax
0x18003487e  jz      short loc_18003488D
0x180034880  jle     short loc_1800348EF
0x180034882  movzx   ebx, ax
0x180034885  or      ebx, 80070000h
0x18003488b  jmp     short loc_1800348EF
0x18003488d  mov     ebx, 80390004h
0x180034892  jmp     short loc_1800348EF
0x180034894  mov     eax, [rbp+FileTime1.dwHighDateTime]
0x180034897  xor     ebx, ebx
0x180034899  mov     ecx, [rdi+78h]
0x18003489c  mov     dword ptr [rbp+var_30+4], eax
0x18003489f  mov     eax, [rbp+FileTime1.dwLowDateTime]
0x1800348a2  mov     dword ptr [rbp+var_30], eax
0x1800348a5  mov     rax, 0C92A69C000h
0x1800348af  imul    rcx, rax
0x1800348b3  mov     rax, [rbp+var_30]
0x1800348b7  add     rax, rcx
0x1800348ba  mov     [rbp+var_30], rax
0x1800348be  shr     rax, 20h
0x1800348c2  mov     [rbp+FileTime1.dwHighDateTime], eax
0x1800348c5  mov     eax, dword ptr [rbp+var_30]
0x1800348c8  mov     [rbp+FileTime1.dwLowDateTime], eax
0x1800348cb  mov     eax, [rdi+74h]
0x1800348ce  cmp     [rbp+var_38], eax
0x1800348d1  jl      short loc_1800348EA
0x1800348d3  lea     rdx, [rbp+FileTime]; lpFileTime2
0x1800348d7  lea     rcx, [rbp+FileTime1]; lpFileTime1
0x1800348db  call    cs:__imp_CompareFileTime
0x1800348e1  test    eax, eax
0x1800348e3  jg      short loc_1800348EA
0x1800348e5  lea     eax, [rbx+1]
0x1800348e8  jmp     short loc_1800348EC
0x1800348ea  xor     eax, eax
0x1800348ec  mov     [r14], eax
0x1800348ef  mov     eax, ebx
0x1800348f1  mov     rcx, [rbp+var_10]
0x1800348f5  xor     rcx, rsp; StackCookie
0x1800348f8  call    __security_check_cookie
0x1800348fd  mov     rbx, [rsp+60h+arg_18]
0x180034905  add     rsp, 60h
0x180034909  pop     r14
0x18003490b  pop     r13
0x18003490d  pop     rdi
0x18003490e  pop     rsi
0x18003490f  pop     rbp
0x180034910  retn
```
