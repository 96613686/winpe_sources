# ConnectedStorage::StorageService::SendPackageStateChange(PACKAGE_EXECUTION_STATE)

- ea: `0x180024f88`
- end: `0x18002508e`
- name: `?SendPackageStateChange@StorageService@ConnectedStorage@@AEAAJW4PACKAGE_EXECUTION_STATE@@@Z`
- size: `262`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021514`
- `0x180021b90`
- `0x180021ba0`

## callees

- `0x180003c70`
- `0x180011b94`
- `0x180024f88`
- `0x18004ae14`
- `0x180084ee0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025055`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180025055`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ConnectedStorage::StorageService::SendPackageStateChange(__int64 a1, __int64 a2, char *a3)
{
  int v3; // esi
  ConnectedStorage::CallerInfoWithResult *v4; // rcx
  const struct ConnectedStorage::CallerInfo *v5; // rbx
  int v6; // edi
  __int128 v7; // xmm6
  unsigned int v9; // [rsp+20h] [rbp-E8h]
  HSTRING newString; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v11[2]; // [rsp+30h] [rbp-D8h] BYREF
  int v12; // [rsp+40h] [rbp-C8h]
  __int128 v13; // [rsp+44h] [rbp-C4h]
  int v14; // [rsp+54h] [rbp-B4h]
  _QWORD *v15; // [rsp+68h] [rbp-A0h]
  HSTRING string; // [rsp+78h] [rbp-90h] BYREF
  int v17; // [rsp+80h] [rbp-88h]
  __int128 v18; // [rsp+84h] [rbp-84h]
  int v19; // [rsp+94h] [rbp-74h]
  _DWORD v20[16]; // [rsp+A0h] [rbp-68h] BYREF

  v3 = a2;
  v9 = 0;
  v4 = (ConnectedStorage::CallerInfoWithResult *)(a1 + 64);
  try
  {
    v5 = ConnectedStorage::CallerInfoWithResult::Get(v4, a2, a3);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, (HSTRING *)v5);
    v6 = *((_DWORD *)v5 + 6);
    v7 = *(_OWORD *)((char *)v5 + 40);
    ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, &newString);
    v17 = v6;
    v18 = v7;
    v19 = v3;
    v11[0] = off_18008FC90;
    v11[1] = string;
    string = 0;
    v12 = v6;
    v13 = v7;
    v14 = v3;
    v15 = v11;
    ConnectedStorage::ExecuteOnThreadPool(v11);
    WindowsDeleteString(string);
    WindowsDeleteString(newString);
  }
  catch ( ConnectedStorage::ComError v20 )
  {
    v9 = v20[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v20);
    return v9;
  }
  catch ( std::bad_alloc )
  {
    return (unsigned int)-2147024882;
  }
  catch ( ... )
  {
    return (unsigned int)-2147467259;
  }
  return v9;
}

```

## disassembly

```asm
0x180024f88  mov     rax, rsp
0x180024f8b  mov     [rax+10h], rbx
0x180024f8f  mov     [rax+18h], rsi
0x180024f93  push    rdi
0x180024f94  sub     rsp, 100h
0x180024f9b  movaps  xmmword ptr [rax-18h], xmm6
0x180024f9f  mov     rax, cs:__security_cookie
0x180024fa6  xor     rax, rsp
0x180024fa9  mov     [rsp+108h+var_28], rax
0x180024fb1  mov     esi, edx
0x180024fb3  mov     [rsp+108h+var_E8], 0
0x180024fbb  add     rcx, 40h ; '@'; this
0x180024fbf  call    ?Get@CallerInfoWithResult@ConnectedStorage@@QEAAAEBVCallerInfo@2@XZ; ConnectedStorage::CallerInfoWithResult::Get(void)
0x180024fc4  mov     rbx, rax
0x180024fc7  mov     rdx, rax; struct ConnectedStorage::SimpleHStringWrapper *
0x180024fca  lea     rcx, [rsp+108h+newString]; newString
0x180024fcf  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180024fd4  nop
0x180024fd5  mov     edi, [rbx+18h]
0x180024fd8  movups  xmm6, xmmword ptr [rbx+28h]
0x180024fdc  lea     rdx, [rsp+108h+newString]; struct ConnectedStorage::SimpleHStringWrapper *
0x180024fe1  lea     rcx, [rsp+108h+string]; newString
0x180024fe6  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180024feb  mov     [rsp+108h+var_88], edi
0x180024ff2  movdqu  [rsp+108h+var_84], xmm6
0x180024ffb  mov     [rsp+108h+var_74], esi
0x180025002  lea     rax, off_18008FC90
0x180025009  mov     [rsp+108h+var_D8], rax
0x18002500e  mov     rax, [rsp+108h+string]
0x180025013  mov     [rsp+108h+var_D0], rax
0x180025018  mov     [rsp+108h+string], 0
0x180025021  mov     [rsp+108h+var_C8], edi
0x180025025  movdqu  [rsp+108h+var_C4], xmm6
0x18002502b  mov     [rsp+108h+var_B4], esi
0x18002502f  lea     rax, [rsp+108h+var_D8]
0x180025034  mov     [rsp+108h+var_A0], rax
0x180025039  lea     rcx, [rsp+108h+var_D8]
0x18002503e  call    ?ExecuteOnThreadPool@ConnectedStorage@@YAXV?$function@$$A6AXXZ@std@@@Z; ConnectedStorage::ExecuteOnThreadPool(std::function<void (void)>)
0x180025043  nop
0x180025044  mov     rcx, [rsp+108h+string]; string
0x180025049  call    cs:__imp_WindowsDeleteString
0x18002504f  nop
0x180025050  mov     rcx, [rsp+108h+newString]; string
0x180025055  call    cs:__imp_WindowsDeleteString
0x18002505b  nop
0x18002505c  mov     eax, [rsp+108h+var_E8]
0x180025060  mov     rcx, [rsp+108h+var_28]
0x180025068  xor     rcx, rsp; StackCookie
0x18002506b  call    __security_check_cookie
0x180025070  lea     r11, [rsp+108h+var_8]
0x180025078  mov     rbx, [r11+18h]
0x18002507c  mov     rsi, [r11+20h]
0x180025080  movaps  xmm6, xmmword ptr [r11-10h]
0x180025085  mov     rsp, r11
0x180025088  pop     rdi
0x180025089  retn
0x18002508a  jmp     short loc_18002505C
0x18002508c  jmp     short loc_18002505C
```
