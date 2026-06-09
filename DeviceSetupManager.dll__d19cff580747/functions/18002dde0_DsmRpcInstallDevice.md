# DsmRpcInstallDevice

- ea: `0x18002dde0`
- end: `0x18002df42`
- name: `DsmRpcInstallDevice`
- size: `354`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180012910`
- `0x18001370c`
- `0x180014908`
- `0x18001985c`
- `0x18001af70`
- `0x18001b3f0`
- `0x18001bc4c`
- `0x18001bcb4`
- `0x180021790`
- `0x180026414`
- `0x18002d35c`
- `0x18002dde0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002deb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002deb8`

## pseudocode

```c
__int64 __fastcall DsmRpcInstallDevice(void *a1)
{
  int UserLanguage; // eax
  __int64 v3; // rcx
  void *v4; // rbx
  unsigned int v5; // edi
  RTL_SRWLOCK *v6; // rdi
  LPVOID pv[2]; // [rsp+30h] [rbp-40h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-30h] BYREF
  std::_Ref_count_base *v10; // [rsp+48h] [rbp-28h]
  __m128i si128; // [rsp+50h] [rbp-20h] BYREF
  int v12; // [rsp+60h] [rbp-10h]
  char v13; // [rsp+64h] [rbp-Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids);
  pv[0] = 0;
  UserLanguage = DsmRpcGetUserLanguage(a1, (unsigned __int16 **)pv);
  v4 = pv[0];
  v5 = UserLanguage;
  if ( UserLanguage >= 0 )
  {
    CDsmCore::GetContainerManager(v3, &SRWLock);
    v6 = SRWLock;
    if ( !SRWLock )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( dword_18005A564 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                     + 4LL) )
    {
      Init_thread_header(&dword_18005A564);
      if ( dword_18005A564 == -1 )
      {
        pv[0] = &si128;
        v12 = 4;
        pv[1] = &v13;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        std::vector<enum JobType>::vector<enum JobType>(&unk_18005A568, pv);
        atexit(DsmRpcInstallDevice_::_5_::_dynamic_atexit_destructor_for__jobs__);
        Init_thread_footer(&dword_18005A564);
      }
    }
    v5 = ContainerManager::PostJobs(v6, (__int64)v4);
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
  }
  if ( v4 )
    CoTaskMemFree(v4);
  return v5;
}

```

## disassembly

```asm
0x18002dde0  mov     [rsp-18h+arg_10], rbx
0x18002dde5  push    rbp
0x18002dde6  push    rsi
0x18002dde7  push    rdi
0x18002dde8  mov     rbp, rsp
0x18002ddeb  sub     rsp, 70h
0x18002ddef  mov     rax, cs:__security_cookie
0x18002ddf6  xor     rax, rsp
0x18002ddf9  mov     [rbp+var_8], rax
0x18002ddfd  mov     rsi, rdx
0x18002de00  mov     rbx, rcx
0x18002de03  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de0a  lea     rax, WPP_GLOBAL_Control
0x18002de11  cmp     rcx, rax
0x18002de14  jz      short loc_18002DE31
0x18002de16  test    byte ptr [rcx+1Ch], 1
0x18002de1a  jz      short loc_18002DE31
0x18002de1c  mov     rcx, [rcx+10h]
0x18002de20  lea     r8, WPP_5382ed2977f13c9d8b4aa53ff18b2f0c_Traceguids
0x18002de27  mov     edx, 19h
0x18002de2c  call    WPP_SF_
0x18002de31  lea     rdx, [rbp+pv]; unsigned __int16 **
0x18002de35  mov     [rbp+pv], 0
0x18002de3d  mov     rcx, rbx; void *
0x18002de40  call    ?DsmRpcGetUserLanguage@@YAJPEAXPEAPEAG@Z; DsmRpcGetUserLanguage(void *,ushort * *)
0x18002de45  mov     rbx, [rbp+pv]
0x18002de49  mov     edi, eax
0x18002de4b  test    eax, eax
0x18002de4d  js      short loc_18002DEB0
0x18002de4f  lea     rdx, [rbp+SRWLock]
0x18002de53  call    ?GetContainerManager@CDsmCore@@QEAA?AV?$shared_ptr@VContainerManager@@@std@@XZ; CDsmCore::GetContainerManager(void)
0x18002de58  mov     rdi, [rbp+SRWLock]
0x18002de5c  test    rdi, rdi
0x18002de5f  jnz     short loc_18002DE66
0x18002de61  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002de66  mov     ecx, cs:_tls_index
0x18002de6c  mov     rax, gs:58h
0x18002de75  mov     edx, 4
0x18002de7a  mov     rax, [rax+rcx*8]
0x18002de7e  mov     eax, [rdx+rax]
0x18002de81  cmp     cs:dword_18005A564, eax
0x18002de87  jg      short loc_18002DEDC
0x18002de89  lea     r8, unk_18005A568
0x18002de90  mov     [rsp+70h+var_50], rbx; __int64
0x18002de95  mov     rdx, rsi
0x18002de98  mov     rcx, rdi; SRWLock
0x18002de9b  call    ?PostJobs@ContainerManager@@QEAAJAEBU_GUID@@AEBV?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@W4JobAttributes@@PEBG@Z; ContainerManager::PostJobs(_GUID const &,std::vector<JobType> const &,JobAttributes,ushort const *)
0x18002dea0  mov     rcx, [rbp+var_28]; this
0x18002dea4  mov     edi, eax
0x18002dea6  test    rcx, rcx
0x18002dea9  jz      short loc_18002DEB0
0x18002deab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002deb0  test    rbx, rbx
0x18002deb3  jz      short loc_18002DEBE
0x18002deb5  mov     rcx, rbx; pv
0x18002deb8  call    cs:__imp_CoTaskMemFree
0x18002debe  mov     eax, edi
0x18002dec0  mov     rcx, [rbp+var_8]
0x18002dec4  xor     rcx, rsp; StackCookie
0x18002dec7  call    __security_check_cookie
0x18002decc  mov     rbx, [rsp+70h+arg_10]
0x18002ded4  add     rsp, 70h
0x18002ded8  pop     rdi
0x18002ded9  pop     rsi
0x18002deda  pop     rbp
0x18002dedb  retn
0x18002dedc  lea     rcx, dword_18005A564
0x18002dee3  call    _Init_thread_header
0x18002dee8  cmp     cs:dword_18005A564, 0FFFFFFFFh
0x18002deef  jnz     short loc_18002DE89
0x18002def1  movdqa  xmm0, cs:__xmm@00000005000000030000000200000000
0x18002def9  lea     rax, [rbp+var_20]
0x18002defd  mov     [rbp+pv], rax
0x18002df01  lea     rdx, [rbp+pv]
0x18002df05  lea     rax, [rbp+var_C]
0x18002df09  mov     [rbp+var_10], 4
0x18002df10  lea     rcx, unk_18005A568
0x18002df17  mov     [rbp+var_38], rax
0x18002df1b  movdqu  [rbp+var_20], xmm0
0x18002df20  call    ??0?$vector@W4JobType@@V?$allocator@W4JobType@@@std@@@std@@QEAA@V?$initializer_list@W4JobType@@@1@AEBV?$allocator@W4JobType@@@1@@Z; std::vector<JobType>::vector<JobType>(std::initializer_list<JobType>,std::allocator<JobType> const &)
0x18002df25  lea     rcx, _DsmRpcInstallDevice____5____dynamic_atexit_destructor_for__jobs__; void (__cdecl *)()
0x18002df2c  call    atexit
0x18002df31  lea     rcx, dword_18005A564
0x18002df38  call    _Init_thread_footer
0x18002df3d  jmp     loc_18002DE89
```
