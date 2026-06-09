# Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateCapability(ushort const *,APPX_CAPABILITY_CLASS_TYPE,bool *)

- ea: `0x18003adec`
- end: `0x18003afb5`
- name: `?ValidateCapability@AppxManifestReaderImpl@Manifest@Packaging@Appx@@AEAAJPEBGW4APPX_CAPABILITY_CLASS_TYPE@@PEA_N@Z`
- size: `457`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::AppxManifestReaderImpl *this, const unsigned __int16 *, unsigned int, bool *)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c8a8`
- `0x1800385d4`
- `0x18003a754`
- `0x18003aaf0`
- `0x1800605ec`
- `0x180066118`
- `0x1800d6040`
- `0x1800d757c`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x18003adec`
- `0x180106010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003aea6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003aea6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aed4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aed4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003af58`

## string_xrefs

- `0x18003af26`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18003af45`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`
- `0x18003af96`: `onecore\printscan\appxpackaging\manifest\src\appxmanifestreader.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::AppxManifestReaderImpl::ValidateCapability(
        Appx::Packaging::Manifest::AppxManifestReaderImpl *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        bool *a4)
{
  char *v7; // rdi
  __int64 v8; // rax
  __int64 (__fastcall *v9)(char *, _QWORD, __int64 *); // rbx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  void *v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-18h] BYREF
  LPVOID pv[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+30h]
  int v21; // [rsp+70h] [rbp+38h] BYREF

  if ( *((_BYTE *)this + 418) )
  {
    *a4 = 1;
    return 0;
  }
  v7 = (char *)this + 16;
  *a4 = 0;
  v8 = *((_QWORD *)this + 2);
  v18 = 0;
  v9 = *(__int64 (__fastcall **)(char *, _QWORD, __int64 *))(v8 + 104);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
  v10 = v9(v7, a3, &v18);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x173C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v10,
      v18);
LABEL_16:
    v17 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  else
  {
    v21 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 32LL))(v18, &v21);
    v11 = v12;
    if ( v12 >= 0 )
    {
      while ( 1 )
      {
        if ( !v21 )
          goto LABEL_10;
        pv[0] = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v18 + 24LL))(v18, pv);
        if ( v11 < 0 )
        {
          v16 = 5955;
          goto LABEL_15;
        }
        if ( !(unsigned int)_o__wcsicmp(a2, pv[0]) )
          break;
        v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 40LL))(v18, &v21);
        if ( v11 < 0 )
        {
          v16 = 5963;
LABEL_15:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v16,
            (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
            (const char *)(unsigned int)v11,
            v18);
          CoTaskMemFree(pv[0]);
          goto LABEL_16;
        }
        CoTaskMemFree(pv[0]);
      }
      v13 = pv[0];
      *a4 = 1;
      CoTaskMemFree(v13);
LABEL_10:
      v14 = v18;
      if ( v18 )
      {
        v18 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x173E,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\appxmanifestreader.cpp",
      (const char *)(unsigned int)v12,
      v18);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v18);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003adec  push    rbp
0x18003adee  push    rbx
0x18003adef  push    rsi
0x18003adf0  push    rdi
0x18003adf1  push    r14
0x18003adf3  push    r15
0x18003adf5  mov     rbp, rsp
0x18003adf8  sub     rsp, 38h
0x18003adfc  cmp     byte ptr [rcx+1A2h], 0
0x18003ae03  mov     rsi, r9
0x18003ae06  mov     r15d, r8d
0x18003ae09  mov     r14, rdx
0x18003ae0c  jnz     loc_18003AF8C
0x18003ae12  lea     rdi, [rcx+10h]
0x18003ae16  mov     byte ptr [r9], 0
0x18003ae1a  mov     rax, [rdi]
0x18003ae1d  lea     rcx, [rbp+var_18]
0x18003ae21  mov     [rbp+var_18], 0
0x18003ae29  mov     rbx, [rax+68h]
0x18003ae2d  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003ae32  lea     r8, [rbp+var_18]
0x18003ae36  mov     edx, r15d
0x18003ae39  mov     rcx, rdi
0x18003ae3c  mov     rax, rbx
0x18003ae3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae44  mov     ebx, eax
0x18003ae46  test    eax, eax
0x18003ae48  js      loc_18003AF22
0x18003ae4e  mov     rcx, [rbp+var_18]
0x18003ae52  lea     rdx, [rbp+arg_0]
0x18003ae56  mov     [rbp+arg_0], 0
0x18003ae5d  mov     rax, [rcx]
0x18003ae60  mov     rax, [rax+20h]
0x18003ae64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae69  mov     ebx, eax
0x18003ae6b  test    eax, eax
0x18003ae6d  js      loc_18003AF92
0x18003ae73  cmp     [rbp+arg_0], 0
0x18003ae77  jz      short loc_18003AEF5
0x18003ae79  mov     rcx, [rbp+var_18]
0x18003ae7d  lea     rdx, [rbp+pv]
0x18003ae81  mov     [rbp+pv], 0
0x18003ae89  mov     rax, [rcx]
0x18003ae8c  mov     rax, [rax+18h]
0x18003ae90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae95  mov     ebx, eax
0x18003ae97  test    eax, eax
0x18003ae99  js      loc_18003AF85
0x18003ae9f  mov     rdx, [rbp+pv]
0x18003aea3  mov     rcx, r14
0x18003aea6  call    cs:__imp__o__wcsicmp
0x18003aead  nop     dword ptr [rax+rax+00h]
0x18003aeb2  test    eax, eax
0x18003aeb4  jz      short loc_18003AEE2
0x18003aeb6  mov     rcx, [rbp+var_18]
0x18003aeba  lea     rdx, [rbp+arg_0]
0x18003aebe  mov     rax, [rcx]
0x18003aec1  mov     rax, [rax+28h]
0x18003aec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aeca  mov     ebx, eax
0x18003aecc  test    eax, eax
0x18003aece  js      short loc_18003AF3C
0x18003aed0  mov     rcx, [rbp+pv]; pv
0x18003aed4  call    cs:__imp_CoTaskMemFree
0x18003aedb  nop     dword ptr [rax+rax+00h]
0x18003aee0  jmp     short loc_18003AE73
0x18003aee2  mov     rcx, [rbp+pv]; pv
0x18003aee6  mov     byte ptr [rsi], 1
0x18003aee9  call    cs:__imp_CoTaskMemFree
0x18003aef0  nop     dword ptr [rax+rax+00h]
0x18003aef5  mov     rcx, [rbp+var_18]
0x18003aef9  test    rcx, rcx
0x18003aefc  jz      short loc_18003AF12
0x18003aefe  mov     [rbp+var_18], 0
0x18003af06  mov     rax, [rcx]
0x18003af09  mov     rax, [rax+10h]
0x18003af0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af12  xor     eax, eax
0x18003af14  add     rsp, 38h
0x18003af18  pop     r15
0x18003af1a  pop     r14
0x18003af1c  pop     rdi
0x18003af1d  pop     rsi
0x18003af1e  pop     rbx
0x18003af1f  pop     rbp
0x18003af20  retn
0x18003af22  mov     rcx, [rbp+30h]; this
0x18003af26  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18003af2d  mov     r9d, ebx; char *
0x18003af30  mov     edx, 173Ch; void *
0x18003af35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003af3a  jmp     short loc_18003AF64
0x18003af3c  mov     edx, 174Bh; void *
0x18003af41  mov     rcx, [rbp+30h]; this
0x18003af45  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18003af4c  mov     r9d, ebx; char *
0x18003af4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003af54  mov     rcx, [rbp+pv]; pv
0x18003af58  call    cs:__imp_CoTaskMemFree
0x18003af5f  nop     dword ptr [rax+rax+00h]
0x18003af64  mov     rcx, [rbp+var_18]
0x18003af68  test    rcx, rcx
0x18003af6b  jz      short loc_18003AF81
0x18003af6d  mov     [rbp+var_18], 0
0x18003af75  mov     rax, [rcx]
0x18003af78  mov     rax, [rax+10h]
0x18003af7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af81  mov     eax, ebx
0x18003af83  jmp     short loc_18003AF14
0x18003af85  mov     edx, 1743h
0x18003af8a  jmp     short loc_18003AF41
0x18003af8c  mov     byte ptr [r9], 1
0x18003af90  jmp     short loc_18003AF12
0x18003af92  mov     rcx, [rbp+30h]; this
0x18003af96  lea     r8, aOnecorePrintsc_127; "onecore\\printscan\\appxpackaging\\mani"...
0x18003af9d  mov     r9d, ebx; char *
0x18003afa0  mov     edx, 173Eh; void *
0x18003afa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003afaa  lea     rcx, [rbp+var_18]
0x18003afae  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18003afb3  jmp     short loc_18003AF81
```
