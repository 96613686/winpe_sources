# SensorGroupClassFactory::CreateSensorGroupCollection(ushort const *,IMFSensorGroupCollection * *)

- ea: `0x180066810`
- end: `0x180066acb`
- name: `?CreateSensorGroupCollection@SensorGroupClassFactory@@UEAAJPEBGPEAPEAUIMFSensorGroupCollection@@@Z`
- size: `699`
- prototype: `__int64 __fastcall(SensorGroupClassFactory *this, const char *, struct IMFSensorGroupCollection **)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008bd0`
- `0x180008f9c`
- `0x18000c348`
- `0x18002c008`
- `0x18002d02c`
- `0x1800401d4`
- `0x180044adc`
- `0x18004ae8c`
- `0x180051018`
- `0x180066810`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800668f3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800668f3`

## pseudocode

```c
__int64 __fastcall SensorGroupClassFactory::CreateSensorGroupCollection(
        SensorGroupClassFactory *this,
        const char *a2,
        struct IMFSensorGroupCollection **a3)
{
  unsigned int v3; // r15d
  const char *v6; // r9
  char *v7; // r14
  __int64 (__fastcall *v8)(SensorGroupClassFactory *, const char *, struct IMFSensorGroup **); // rbx
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  char *v12; // rsi
  __int64 v13; // rcx
  __int64 v14; // r13
  __int64 (__fastcall ***v15)(_QWORD, GUID *, struct IMFSensorGroup **); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, struct IMFSensorGroup **); // rbx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v20; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v21; // [rsp+38h] [rbp-18h]
  __int64 v22; // [rsp+3Ch] [rbp-14h]
  struct IMFSensorGroup *v23; // [rsp+90h] [rbp+40h] BYREF
  struct IMFSensorGroupCollection **v24; // [rsp+A0h] [rbp+50h]
  char *v25; // [rsp+A8h] [rbp+58h] BYREF

  v24 = a3;
  v3 = 0;
  v23 = 0;
  v25 = 0;
  v20 = 0;
  v22 = 0;
  v21 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v6 = a2;
    if ( !a2 )
      v6 = L"<nullptr>";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 27), 81, &WPP_09150840c5f230171d137cf28cc6c946_Traceguids, v6);
  }
  v7 = (char *)this - 8;
  v8 = *(__int64 (__fastcall **)(SensorGroupClassFactory *, const char *, struct IMFSensorGroup **))(*(_QWORD *)this + 24LL);
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v23);
  v9 = v8(this, a2, &v23);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_33;
    v11 = 82;
    goto LABEL_8;
  }
  v12 = (char *)operator new(0x50u);
  if ( v12 )
  {
    *((_DWORD *)v12 + 2) = 1;
    *(_QWORD *)v12 = &SensorGroupCollection::`vftable';
    InitializeCriticalSection((LPCRITICAL_SECTION)(v12 + 16));
    *((_QWORD *)v12 + 7) = 0;
    *(_QWORD *)(v12 + 68) = 0;
    *((_DWORD *)v12 + 16) = 0;
    v25 = v12;
    v9 = SensorGroupCollection::AddSensorGroup((SensorGroupCollection *)v12, v23);
    v10 = v9;
    if ( v9 >= 0 )
    {
      v9 = CollectAllSensorGroups(v13, &v20);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v14 = v20;
        while ( v3 < v21 )
        {
          if ( IsDeviceInSensorGroup(*(struct IMFSensorGroupInternal **)(v14 + 8LL * v3), (const unsigned __int16 *)a2) )
          {
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v23);
            v15 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IMFSensorGroup **))(v14 + 8LL * v3);
            v16 = **v15;
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v23);
            v9 = v16(v15, &GUID_4110243a_9757_461f_89f1_f22345bcab4e, &v23);
            v10 = v9;
            if ( v9 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_33;
              v11 = 86;
              goto LABEL_8;
            }
            v9 = SensorGroupCollection::AddSensorGroup((SensorGroupCollection *)v12, v23);
            v10 = v9;
            if ( v9 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_33;
              v11 = 87;
              goto LABEL_8;
            }
          }
          ++v3;
        }
        v9 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IMFSensorGroupCollection **))v12)(
               v12,
               &GUID_560a0c60_5e50_4429_8c59_c7de0812096c,
               v24);
        v10 = v9;
        if ( v9 >= 0 )
        {
          if ( (unsigned __int8)byte_18008D62D < 8u )
            goto LABEL_36;
          v17 = 90;
          v18 = (unsigned int)v9;
          goto LABEL_35;
        }
        if ( !g_wppLevels )
          goto LABEL_33;
        v11 = 88;
        goto LABEL_8;
      }
      if ( g_wppLevels )
      {
        v11 = 85;
        goto LABEL_8;
      }
    }
    else if ( g_wppLevels )
    {
      v11 = 84;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_09150840c5f230171d137cf28cc6c946_Traceguids, v7, v9);
    }
  }
  else
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        83,
        &WPP_09150840c5f230171d137cf28cc6c946_Traceguids,
        v7,
        -2147024882);
  }
LABEL_33:
  if ( byte_18008D62D )
  {
    v17 = 89;
    v18 = v10;
LABEL_35:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v17, &WPP_09150840c5f230171d137cf28cc6c946_Traceguids, v18);
  }
LABEL_36:
  CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(&v20);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v25);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v23);
  return v10;
}

```

## disassembly

```asm
0x180066810  mov     [rsp-38h+arg_8], rbx
0x180066815  mov     [rsp-38h+arg_10], r8
0x18006681a  push    rbp
0x18006681b  push    rsi
0x18006681c  push    rdi
0x18006681d  push    r12
0x18006681f  push    r13
0x180066821  push    r14
0x180066823  push    r15
0x180066825  mov     rbp, rsp
0x180066828  sub     rsp, 50h
0x18006682c  xor     r15d, r15d
0x18006682f  mov     r12, rdx
0x180066832  mov     [rbp+arg_0], r15
0x180066836  mov     rdi, rcx
0x180066839  mov     [rbp+arg_18], r15
0x18006683d  mov     [rbp+var_20], r15
0x180066841  mov     [rbp+var_14], r15
0x180066845  mov     [rbp+var_18], r15d
0x180066849  cmp     cs:byte_18008D62D, 8
0x180066850  jb      short loc_180066881
0x180066852  mov     rcx, cs:WPP_GLOBAL_Control
0x180066859  lea     rax, aNullptr; "<nullptr>"
0x180066860  test    rdx, rdx
0x180066863  lea     r8, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x18006686a  mov     r9, rdx
0x18006686d  lea     edx, [r15+51h]
0x180066871  cmovz   r9, rax
0x180066875  mov     rcx, [rcx+0D8h]
0x18006687c  call    WPP_SF_S
0x180066881  mov     rax, [rdi]
0x180066884  lea     rcx, [rbp+arg_0]
0x180066888  lea     r14, [rdi-8]
0x18006688c  mov     rbx, [rax+18h]
0x180066890  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180066895  lea     r8, [rbp+arg_0]
0x180066899  mov     rdx, r12
0x18006689c  mov     rcx, rdi
0x18006689f  mov     rax, rbx
0x1800668a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668a7  mov     ebx, eax
0x1800668a9  test    eax, eax
0x1800668ab  jns     short loc_1800668C8
0x1800668ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800668b4  jb      loc_180066A6B
0x1800668ba  mov     edx, 52h ; 'R'
0x1800668bf  mov     [rsp+50h+var_30], eax
0x1800668c3  jmp     loc_180066A51
0x1800668c8  mov     ecx, 50h ; 'P'; Size
0x1800668cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800668d2  mov     rsi, rax
0x1800668d5  test    rax, rax
0x1800668d8  jz      loc_180066A3A
0x1800668de  lea     rax, ??_7SensorGroupCollection@@6B@; const SensorGroupCollection::`vftable'
0x1800668e5  mov     dword ptr [rsi+8], 1
0x1800668ec  lea     rcx, [rsi+10h]; lpCriticalSection
0x1800668f0  mov     [rsi], rax
0x1800668f3  call    cs:__imp_InitializeCriticalSection
0x1800668f9  mov     [rsi+38h], r15
0x1800668fd  mov     rcx, rsi; this
0x180066900  mov     [rsi+44h], r15
0x180066904  mov     [rsi+40h], r15d
0x180066908  mov     rdx, [rbp+arg_0]; struct IMFSensorGroup *
0x18006690c  mov     [rbp+arg_18], rsi
0x180066910  call    ?AddSensorGroup@SensorGroupCollection@@QEAAJPEAUIMFSensorGroup@@@Z; SensorGroupCollection::AddSensorGroup(IMFSensorGroup *)
0x180066915  mov     ebx, eax
0x180066917  test    eax, eax
0x180066919  jns     short loc_18006692F
0x18006691b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066922  jb      loc_180066A6B
0x180066928  mov     edx, 54h ; 'T'
0x18006692d  jmp     short loc_1800668BF
0x18006692f  lea     rdx, [rbp+var_20]
0x180066933  call    ?CollectAllSensorGroups@@YAJAEBU_GUID@@AEAV?$CTUnkArray@UIMFSensorGroupInternal@@@@@Z; CollectAllSensorGroups(_GUID const &,CTUnkArray<IMFSensorGroupInternal> &)
0x180066938  mov     ebx, eax
0x18006693a  test    eax, eax
0x18006693c  jns     short loc_180066955
0x18006693e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066945  jb      loc_180066A6B
0x18006694b  mov     edx, 55h ; 'U'
0x180066950  jmp     loc_1800668BF
0x180066955  mov     r13, [rbp+var_20]
0x180066959  cmp     r15d, [rbp+var_18]
0x18006695d  jnb     loc_1800669F5
0x180066963  mov     edi, r15d
0x180066966  mov     rdx, r12; unsigned __int16 *
0x180066969  mov     rcx, [r13+rdi*8+0]; struct IMFSensorGroupInternal *
0x18006696e  call    ?IsDeviceInSensorGroup@@YA_NPEAUIMFSensorGroupInternal@@PEBG@Z; IsDeviceInSensorGroup(IMFSensorGroupInternal *,ushort const *)
0x180066973  test    al, al
0x180066975  jz      short loc_1800669C2
0x180066977  lea     rcx, [rbp+arg_0]
0x18006697b  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180066980  mov     rdi, [r13+rdi*8+0]
0x180066985  lea     rcx, [rbp+arg_0]
0x180066989  mov     rax, [rdi]
0x18006698c  mov     rbx, [rax]
0x18006698f  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180066994  lea     r8, [rbp+arg_0]
0x180066998  mov     rcx, rdi
0x18006699b  lea     rdx, _GUID_4110243a_9757_461f_89f1_f22345bcab4e
0x1800669a2  mov     rax, rbx
0x1800669a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669aa  mov     ebx, eax
0x1800669ac  test    eax, eax
0x1800669ae  js      short loc_1800669DE
0x1800669b0  mov     rdx, [rbp+arg_0]; struct IMFSensorGroup *
0x1800669b4  mov     rcx, rsi; this
0x1800669b7  call    ?AddSensorGroup@SensorGroupCollection@@QEAAJPEAUIMFSensorGroup@@@Z; SensorGroupCollection::AddSensorGroup(IMFSensorGroup *)
0x1800669bc  mov     ebx, eax
0x1800669be  test    eax, eax
0x1800669c0  js      short loc_1800669C7
0x1800669c2  inc     r15d
0x1800669c5  jmp     short loc_180066959
0x1800669c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800669ce  jb      loc_180066A6B
0x1800669d4  mov     edx, 57h ; 'W'
0x1800669d9  jmp     loc_1800668BF
0x1800669de  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800669e5  jb      loc_180066A6B
0x1800669eb  mov     edx, 56h ; 'V'
0x1800669f0  jmp     loc_1800668BF
0x1800669f5  mov     rax, [rsi]
0x1800669f8  lea     rdx, _GUID_560a0c60_5e50_4429_8c59_c7de0812096c
0x1800669ff  mov     r8, [rbp+arg_10]
0x180066a03  mov     rcx, rsi
0x180066a06  mov     rax, [rax]
0x180066a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066a0e  mov     ebx, eax
0x180066a10  test    eax, eax
0x180066a12  jns     short loc_180066A27
0x180066a14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066a1b  jb      short loc_180066A6B
0x180066a1d  mov     edx, 58h ; 'X'
0x180066a22  jmp     loc_1800668BF
0x180066a27  cmp     cs:byte_18008D62D, 8
0x180066a2e  jb      short loc_180066A96
0x180066a30  mov     edx, 5Ah ; 'Z'
0x180066a35  mov     r9d, eax
0x180066a38  jmp     short loc_180066A7C
0x180066a3a  mov     ebx, 8007000Eh
0x180066a3f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180066a46  jb      short loc_180066A6B
0x180066a48  mov     edx, 53h ; 'S'
0x180066a4d  mov     [rsp+50h+var_30], ebx
0x180066a51  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a58  lea     r8, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x180066a5f  mov     r9, r14
0x180066a62  mov     rcx, [rcx+10h]
0x180066a66  call    WPP_SF_qD
0x180066a6b  cmp     cs:byte_18008D62D, 1
0x180066a72  jb      short loc_180066A96
0x180066a74  mov     edx, 59h ; 'Y'
0x180066a79  mov     r9d, ebx
0x180066a7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066a83  lea     r8, WPP_09150840c5f230171d137cf28cc6c946_Traceguids
0x180066a8a  mov     rcx, [rcx+0D8h]
0x180066a91  call    WPP_SF_d
0x180066a96  lea     rcx, [rbp+var_20]; void *
0x180066a9a  call    ??1?$CTUnkArray@UIMFSensorDevice@@@@QEAA@XZ; CTUnkArray<IMFSensorDevice>::~CTUnkArray<IMFSensorDevice>(void)
0x180066a9f  lea     rcx, [rbp+arg_18]
0x180066aa3  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180066aa8  lea     rcx, [rbp+arg_0]
0x180066aac  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180066ab1  mov     eax, ebx
0x180066ab3  mov     rbx, [rsp+50h+arg_8]
0x180066abb  add     rsp, 50h
0x180066abf  pop     r15
0x180066ac1  pop     r14
0x180066ac3  pop     r13
0x180066ac5  pop     r12
0x180066ac7  pop     rdi
0x180066ac8  pop     rsi
0x180066ac9  pop     rbp
0x180066aca  retn
```
