# RetailDemoUtil::IsAppRunning(ushort const *,bool *,void *)

- ea: `0x18003106c`
- end: `0x18003127e`
- name: `?IsAppRunning@RetailDemoUtil@@YAJPEBGPEA_NPEAX@Z`
- size: `530`
- prototype: `__int64 __fastcall(RetailDemoUtil *__hidden this, const unsigned __int16 *, bool *, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180032590`

## callees

- `0x18000e3bc`
- `0x18001094c`
- `0x180010a60`
- `0x180022298`
- `0x18002231c`
- `0x180022448`
- `0x18003106c`
- `0x180046c84`
- `0x180046e6c`

## import_xrefs

- `RMCLIENT!HamConnectForDebugging` at `0x1800311a3`
- `RMCLIENT!HamConnectForDebugging` at `0x1800311a3`
- `RMCLIENT!HamDisconnectFromServer` at `0x18003121e`
- `RMCLIENT!HamDisconnectFromServer` at `0x18003121e`
- `RMCLIENT!HamDebugClosePackageHandle` at `0x18003120e`
- `RMCLIENT!HamDebugClosePackageHandle` at `0x18003120e`
- `RMCLIENT!HamDebugQueryPackageState` at `0x1800311ea`
- `RMCLIENT!HamDebugQueryPackageState` at `0x1800311ea`
- `RMCLIENT!HamFreeBuffer` at `0x18003122e`
- `RMCLIENT!HamFreeBuffer` at `0x18003122e`
- `RMCLIENT!HamDebugOpenPackageHandle` at `0x1800311bf`
- `RMCLIENT!HamDebugOpenPackageHandle` at `0x1800311bf`

## string_xrefs

- `0x180031167`: `shellcommon\shell\retaildemo\util\retaildemoutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall RetailDemoUtil::IsAppRunning(RetailDemoUtil *this, unsigned __int16 *a2, bool *a3, void *a4)
{
  unsigned __int64 v7; // rbx
  int v8; // edi
  unsigned __int16 **v9; // r8
  const char *v10; // r9
  __int64 result; // rax
  int v12; // [rsp+20h] [rbp-98h]
  __int64 v13; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int16 v14[4]; // [rsp+38h] [rbp-80h] BYREF
  PCWSTR packageFamilyName; // [rsp+40h] [rbp-78h] BYREF
  __int64 v16; // [rsp+48h] [rbp-70h]
  __int64 v17; // [rsp+50h] [rbp-68h]
  int v18; // [rsp+58h] [rbp-60h] BYREF
  __int64 v19; // [rsp+60h] [rbp-58h] BYREF
  __int64 v20; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int16 *v21; // [rsp+70h] [rbp-48h] BYREF
  __int64 v22; // [rsp+78h] [rbp-40h]
  __int64 v23; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v25; // [rsp+D8h] [rbp+20h] BYREF

  v13 = 0;
  v25 = 0;
  v19 = -1;
  *(_QWORD *)v14 = 0;
  packageFamilyName = 0;
  v16 = 0;
  v17 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v20 = 0;
  v18 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
  v22 = -1;
  v23 = -1;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&packageFamilyName);
  v16 = -1;
  v17 = -1;
  try
  {
    if ( (unsigned int)ParseAppUserModelId(
                         (const unsigned __int16 *)this,
                         (unsigned __int16 **)&packageFamilyName,
                         &v21) == -2147024809 )
    {
      if ( this )
      {
        v7 = -1;
        do
          ++v7;
        while ( *((_WORD *)this + v7) );
        v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
               (__int64)&packageFamilyName,
               v7);
        if ( v8 >= 0 )
        {
          StringCchCopyNW((unsigned __int16 *)packageFamilyName, v7 + 1, (const unsigned __int16 *)this, v7);
          v16 = v7;
        }
      }
      else
      {
        v8 = 0;
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&packageFamilyName);
      }
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3A8,
          (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
          (const char *)(unsigned int)v8,
          v12);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      v14,
      0);
    if ( (int)CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(packageFamilyName, v14, v9) >= 0
      && (int)HamConnectForDebugging(TaskBase<enum RetailDemoTaskResult,0,0,12>::HandleExecutionFailure, &v13) >= 0
      && (int)HamDebugOpenPackageHandle(v13, *(_QWORD *)v14, a3, &v19) >= 0 )
    {
      HamDebugQueryPackageState(v13, v19, &v25, &v20, &v18);
      *(_BYTE *)a2 = (v25 & 0x400) != 0;
    }
    if ( v19 != -1 )
      HamDebugClosePackageHandle(v13);
    if ( v13 )
      HamDisconnectFromServer();
    if ( v20 )
      HamFreeBuffer();
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v21);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&packageFamilyName);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v14);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3BF,
                           (unsigned int)"shellcommon\\shell\\retaildemo\\util\\retaildemoutil.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18003106c  mov     rax, rsp
0x18003106f  mov     [rax+8], rbx
0x180031073  mov     [rax+10h], rsi
0x180031077  push    rdi
0x180031078  push    r12
0x18003107a  push    r13
0x18003107c  push    r14
0x18003107e  push    r15
0x180031080  sub     rsp, 90h
0x180031087  mov     r14, r8
0x18003108a  mov     r15, rdx
0x18003108d  mov     rsi, rcx
0x180031090  xor     r12d, r12d
0x180031093  mov     [rsp+0B8h+var_88], r12
0x180031098  mov     [rax+20h], r12d
0x18003109c  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800310a0  mov     [rax-58h], r13
0x1800310a4  mov     [rax-80h], r12
0x1800310a8  mov     [rax-78h], r12
0x1800310ac  mov     [rax-70h], r12
0x1800310b0  mov     [rax-68h], r12
0x1800310b4  mov     [rax-48h], r12
0x1800310b8  mov     [rax-40h], r12
0x1800310bc  mov     [rax-38h], r12
0x1800310c0  mov     [rax-50h], r12
0x1800310c4  mov     [rax-60h], r12d
0x1800310c8  lea     rcx, [rax-48h]
0x1800310cc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800310d1  mov     [rsp+0B8h+var_40], r13
0x1800310d6  mov     [rsp+0B8h+var_38], r13
0x1800310de  lea     rcx, [rsp+0B8h+packageFamilyName]
0x1800310e3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800310e8  mov     [rsp+0B8h+var_70], r13
0x1800310ed  mov     [rsp+0B8h+var_68], r13
0x1800310f2  lea     r8, [rsp+0B8h+var_48]; unsigned __int16 **
0x1800310f7  lea     rdx, [rsp+0B8h+packageFamilyName]; unsigned __int16 **
0x1800310fc  mov     rcx, rsi; unsigned __int16 *
0x1800310ff  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x180031104  cmp     eax, 80070057h
0x180031109  jnz     short loc_180031178
0x18003110b  test    rsi, rsi
0x18003110e  jz      short loc_18003114B
0x180031110  mov     rbx, r13
0x180031113  inc     rbx
0x180031116  cmp     [rsi+rbx*2], r12w
0x18003111b  jnz     short loc_180031113
0x18003111d  mov     rdx, rbx
0x180031120  lea     rcx, [rsp+0B8h+packageFamilyName]
0x180031125  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x18003112a  mov     edi, eax
0x18003112c  test    eax, eax
0x18003112e  js      short loc_180031158
0x180031130  lea     rdx, [rbx+1]; unsigned __int64
0x180031134  mov     r9, rbx; unsigned __int64
0x180031137  mov     r8, rsi; unsigned __int16 *
0x18003113a  mov     rcx, [rsp+0B8h+packageFamilyName]; unsigned __int16 *
0x18003113f  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180031144  mov     [rsp+0B8h+var_70], rbx
0x180031149  jmp     short loc_180031158
0x18003114b  mov     edi, r12d
0x18003114e  lea     rcx, [rsp+0B8h+packageFamilyName]
0x180031153  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031158  mov     rcx, [rsp+0B8h]; this
0x180031160  test    edi, edi
0x180031162  jns     short loc_180031178
0x180031164  mov     r9d, edi; char *
0x180031167  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\retaildemo\\util\\r"...
0x18003116e  mov     edx, 3A8h; void *
0x180031173  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031178  xor     edx, edx
0x18003117a  lea     rcx, [rsp+0B8h+var_80]
0x18003117f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180031184  lea     rdx, [rsp+0B8h+var_80]; unsigned __int16 *
0x180031189  mov     rcx, [rsp+0B8h+packageFamilyName]; packageFamilyName
0x18003118e  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)
0x180031193  test    eax, eax
0x180031195  js      short loc_1800311FF
0x180031197  lea     rdx, [rsp+0B8h+var_88]
0x18003119c  lea     rcx, ?HandleExecutionFailure@?$TaskBase@W4RetailDemoTaskResult@@$0A@$0A@$0M@@@MEAAXJ@Z; TaskBase<RetailDemoTaskResult,0,0,12>::HandleExecutionFailure(long)
0x1800311a3  call    cs:__imp_HamConnectForDebugging
0x1800311a9  test    eax, eax
0x1800311ab  js      short loc_1800311FF
0x1800311ad  lea     r9, [rsp+0B8h+var_58]
0x1800311b2  mov     r8, r14
0x1800311b5  mov     rdx, qword ptr [rsp+0B8h+var_80]
0x1800311ba  mov     rcx, [rsp+0B8h+var_88]
0x1800311bf  call    cs:__imp_HamDebugOpenPackageHandle
0x1800311c5  test    eax, eax
0x1800311c7  js      short loc_1800311FF
0x1800311c9  lea     rax, [rsp+0B8h+var_60]
0x1800311ce  mov     qword ptr [rsp+0B8h+var_98], rax
0x1800311d3  lea     r9, [rsp+0B8h+var_50]
0x1800311d8  lea     r8, [rsp+0B8h+arg_18]
0x1800311e0  mov     rdx, [rsp+0B8h+var_58]
0x1800311e5  mov     rcx, [rsp+0B8h+var_88]
0x1800311ea  call    cs:__imp_HamDebugQueryPackageState
0x1800311f0  mov     eax, [rsp+0B8h+arg_18]
0x1800311f7  shr     eax, 0Ah
0x1800311fa  and     al, 1
0x1800311fc  mov     [r15], al
0x1800311ff  mov     rdx, [rsp+0B8h+var_58]
0x180031204  cmp     rdx, r13
0x180031207  jz      short loc_180031214
0x180031209  mov     rcx, [rsp+0B8h+var_88]
0x18003120e  call    cs:__imp_HamDebugClosePackageHandle
0x180031214  mov     rcx, [rsp+0B8h+var_88]
0x180031219  test    rcx, rcx
0x18003121c  jz      short loc_180031224
0x18003121e  call    cs:__imp_HamDisconnectFromServer
0x180031224  mov     rcx, [rsp+0B8h+var_50]
0x180031229  test    rcx, rcx
0x18003122c  jz      short loc_180031235
0x18003122e  call    cs:__imp_HamFreeBuffer
0x180031234  nop
0x180031235  lea     rcx, [rsp+0B8h+var_48]
0x18003123a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003123f  nop
0x180031240  lea     rcx, [rsp+0B8h+packageFamilyName]
0x180031245  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003124a  nop
0x18003124b  lea     rcx, [rsp+0B8h+var_80]
0x180031250  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180031255  xor     eax, eax
0x180031257  jmp     short loc_180031260
0x180031259  mov     eax, [rsp+0B8h+arg_18]
0x180031260  lea     r11, [rsp+0B8h+var_28]
0x180031268  mov     rbx, [r11+30h]
0x18003126c  mov     rsi, [r11+38h]
0x180031270  mov     rsp, r11
0x180031273  pop     r15
0x180031275  pop     r14
0x180031277  pop     r13
0x180031279  pop     r12
0x18003127b  pop     rdi
0x18003127c  retn
```
