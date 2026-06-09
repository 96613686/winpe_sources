# CGuestAudioEndpointVolume::RegisterControlChangeNotify(IAudioEndpointVolumeCallback *)

- ea: `0x1800817a0`
- end: `0x180081951`
- name: `?RegisterControlChangeNotify@CGuestAudioEndpointVolume@@EEAAJPEAUIAudioEndpointVolumeCallback@@@Z`
- size: `433`
- prototype: `__int64 __fastcall(CGuestAudioEndpointVolume *__hidden this, struct IAudioEndpointVolumeCallback *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x180010a90`
- `0x18004d8a8`
- `0x1800817a0`
- `0x180081958`
- `0x1800b4c90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800817e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800817e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008188f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800818f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081937`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008188f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800818f4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081937`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800818e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008190f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800818e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008190f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGuestAudioEndpointVolume::RegisterControlChangeNotify(
        CGuestAudioEndpointVolume *this,
        struct IAudioEndpointVolumeCallback *a2)
{
  __int64 result; // rax
  unsigned int v4; // edi
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  int v6; // r8d
  int v7; // edi
  const char *v8; // r9
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx
  int v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  int v14[4]; // [rsp+30h] [rbp-48h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-38h] BYREF
  __int64 v16; // [rsp+48h] [rbp-30h] BYREF
  char v17; // [rsp+50h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  struct IAudioEndpointVolumeCallback *v19; // [rsp+88h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+90h] [rbp+18h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+98h] [rbp+20h]

  v19 = a2;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
      (const char *)0x80004003LL,
      v12);
    return 2147500035LL;
  }
  v4 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  try
  {
    v21 = v5;
    if ( !*((_BYTE *)this + 256) )
    {
      pv = 0;
      p_pv = &pv;
      v16 = 0;
      v17 = 1;
      LOBYTE(v6) = 0;
      v7 = CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeRegisterControlChanged>(
             (int)this + 16,
             *((_DWORD *)this + 16),
             v6,
             (unsigned int)&v16,
             (__int64)v14);
      wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3C,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
          (const char *)(unsigned int)v7,
          v13);
        v9 = pv;
        pv = 0;
        if ( v9 )
          CoTaskMemFree(v9);
        if ( v5 )
          LeaveCriticalSection(v5);
        return (unsigned int)v7;
      }
      *((_BYTE *)this + 256) = 1;
      v10 = pv;
      v4 = *((_DWORD *)pv + 1);
      if ( (v4 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40,
          (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
          (const char *)v4,
          v13);
        v11 = pv;
        pv = 0;
        if ( v11 )
          CoTaskMemFree(v11);
        if ( v5 )
          LeaveCriticalSection(v5);
        return v4;
      }
      pv = 0;
      if ( v10 )
        CoTaskMemFree(v10);
    }
    std::_Hash<std::_Uset_traits<IAudioEndpointVolumeCallback *,std::_Uhash_compare<IAudioEndpointVolumeCallback *,std::hash<IAudioEndpointVolumeCallback *>,std::equal_to<IAudioEndpointVolumeCallback *>>,std::allocator<IAudioEndpointVolumeCallback *>,0>>::emplace<IAudioEndpointVolumeCallback * const &>(
      (char *)this + 152,
      v14,
      &v19);
    if ( v5 )
      LeaveCriticalSection(v5);
    result = v4;
  }
  catch ( ... )
  {
    LODWORD(v19) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x47,
                     (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientvolume.cpp",
                     v8);
    return (unsigned int)v19;
  }
  return result;
}

```

## disassembly

```asm
0x1800817a0  mov     [rsp+arg_8], rdx
0x1800817a5  push    rbx
0x1800817a6  push    rsi
0x1800817a7  push    rdi
0x1800817a8  sub     rsp, 60h
0x1800817ac  mov     rsi, rcx
0x1800817af  test    rdx, rdx
0x1800817b2  jnz     short loc_1800817D9
0x1800817b4  mov     rcx, [rsp+78h]; this
0x1800817b9  mov     ebx, 80004003h
0x1800817be  mov     r9d, ebx; char *
0x1800817c1  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x1800817c8  mov     edx, 32h ; '2'; void *
0x1800817cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800817d2  mov     eax, ebx
0x1800817d4  jmp     loc_180081948
0x1800817d9  xor     edi, edi
0x1800817db  lea     rbx, [rcx+0D8h]
0x1800817e2  mov     rcx, rbx; lpCriticalSection
0x1800817e5  call    cs:__imp_EnterCriticalSection
0x1800817eb  mov     [rsp+78h+arg_18], rbx
0x1800817f3  cmp     [rsi+100h], dil
0x1800817fa  jnz     loc_180081915
0x180081800  mov     [rsp+78h+pv], rdi
0x180081808  lea     rax, [rsp+78h+pv]
0x180081810  mov     [rsp+78h+var_38], rax
0x180081815  mov     [rsp+78h+var_30], rdi
0x18008181a  mov     [rsp+78h+var_28], 1
0x18008181f  xor     r8b, r8b
0x180081822  lea     rcx, [rsi+10h]
0x180081826  lea     rax, [rsp+78h+var_48]
0x18008182b  mov     qword ptr [rsp+78h+var_58], rax; int
0x180081830  lea     r9, [rsp+78h+var_30]
0x180081835  mov     edx, [rsi+40h]
0x180081838  call    ??$SendAndValidateResponse@UXvmAudioEndpointVolumeRegisterControlChanged@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeRegisterControlChanged@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeRegisterControlChanged>(uint,XvmAudioEndpointVolumeRegisterControlChanged,XvmMessage * *,XvmAudioEndpointVolumeRegisterControlChanged * *)
0x18008183d  mov     edi, eax
0x18008183f  lea     rcx, [rsp+78h+var_38]
0x180081844  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180081849  test    edi, edi
0x18008184b  jns     short loc_18008189C
0x18008184d  mov     rcx, [rsp+78h]; this
0x180081852  mov     r9d, edi; char *
0x180081855  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x18008185c  mov     edx, 3Ch ; '<'; void *
0x180081861  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081866  nop
0x180081867  mov     rcx, [rsp+78h+pv]; pv
0x18008186f  mov     [rsp+78h+pv], 0
0x18008187b  test    rcx, rcx
0x18008187e  jz      short loc_180081887
0x180081880  call    cs:__imp_CoTaskMemFree
0x180081886  nop
0x180081887  test    rbx, rbx
0x18008188a  jz      short loc_180081895
0x18008188c  mov     rcx, rbx; lpCriticalSection
0x18008188f  call    cs:__imp_LeaveCriticalSection
0x180081895  mov     eax, edi
0x180081897  jmp     loc_180081948
0x18008189c  mov     byte ptr [rsi+100h], 1
0x1800818a3  mov     rcx, [rsp+78h+pv]; pv
0x1800818ab  mov     edi, [rcx+4]
0x1800818ae  test    edi, edi
0x1800818b0  jns     short loc_1800818FE
0x1800818b2  mov     rcx, [rsp+78h]; this
0x1800818b7  mov     r9d, edi; char *
0x1800818ba  lea     r8, aAvcoreAudiocor_4; "avcore\\audiocore\\client\\audioclient"...
0x1800818c1  mov     edx, 40h ; '@'; void *
0x1800818c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800818cb  nop
0x1800818cc  mov     rcx, [rsp+78h+pv]; pv
0x1800818d4  mov     [rsp+78h+pv], 0
0x1800818e0  test    rcx, rcx
0x1800818e3  jz      short loc_1800818EC
0x1800818e5  call    cs:__imp_CoTaskMemFree
0x1800818eb  nop
0x1800818ec  test    rbx, rbx
0x1800818ef  jz      short loc_1800818FA
0x1800818f1  mov     rcx, rbx; lpCriticalSection
0x1800818f4  call    cs:__imp_LeaveCriticalSection
0x1800818fa  mov     eax, edi
0x1800818fc  jmp     short loc_180081948
0x1800818fe  mov     [rsp+78h+pv], 0
0x18008190a  test    rcx, rcx
0x18008190d  jz      short loc_180081915
0x18008190f  call    cs:__imp_CoTaskMemFree
0x180081915  lea     rcx, [rsi+98h]
0x18008191c  lea     r8, [rsp+78h+arg_8]
0x180081924  lea     rdx, [rsp+78h+var_48]
0x180081929  call    ??$emplace@AEBQEAUIAudioEndpointVolumeCallback@@@?$_Hash@V?$_Uset_traits@PEAUIAudioEndpointVolumeCallback@@V?$_Uhash_compare@PEAUIAudioEndpointVolumeCallback@@U?$hash@PEAUIAudioEndpointVolumeCallback@@@std@@U?$equal_to@PEAUIAudioEndpointVolumeCallback@@@3@@std@@V?$allocator@PEAUIAudioEndpointVolumeCallback@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAUIAudioEndpointVolumeCallback@@@std@@@std@@@std@@_N@1@AEBQEAUIAudioEndpointVolumeCallback@@@Z; std::_Hash<std::_Uset_traits<IAudioEndpointVolumeCallback *,std::_Uhash_compare<IAudioEndpointVolumeCallback *,std::hash<IAudioEndpointVolumeCallback *>,std::equal_to<IAudioEndpointVolumeCallback *>>,std::allocator<IAudioEndpointVolumeCallback *>,0>>::emplace<IAudioEndpointVolumeCallback * const &>(IAudioEndpointVolumeCallback * const &)
0x18008192e  nop
0x18008192f  test    rbx, rbx
0x180081932  jz      short loc_18008193D
0x180081934  mov     rcx, rbx; lpCriticalSection
0x180081937  call    cs:__imp_LeaveCriticalSection
0x18008193d  mov     eax, edi
0x18008193f  jmp     short loc_180081948
0x180081941  mov     eax, dword ptr [rsp+78h+arg_8]
0x180081948  add     rsp, 60h
0x18008194c  pop     rdi
0x18008194d  pop     rsi
0x18008194e  pop     rbx
0x18008194f  retn
```
