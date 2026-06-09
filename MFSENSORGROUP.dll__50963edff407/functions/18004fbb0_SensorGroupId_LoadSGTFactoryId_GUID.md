# SensorGroupId::LoadSGTFactoryId(_GUID *)

- ea: `0x18004fbb0`
- end: `0x18004fe0f`
- name: `?LoadSGTFactoryId@SensorGroupId@@UEAAJPEAU_GUID@@@Z`
- size: `607`
- prototype: `int(SensorGroupId *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000a450`
- `0x1800261a8`
- `0x180044b1c`
- `0x180044b28`
- `0x180045900`
- `0x18004fbb0`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fdef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fdef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fbd1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004fbd1`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18004fc7e`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18004fc7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004fc94`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18004fd9f`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18004fd9f`

## pseudocode

```c
__int64 __fastcall SensorGroupId::LoadSGTFactoryId(SensorGroupId *this, struct _GUID *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  char *v5; // rbp
  unsigned int v6; // esi
  __int64 v7; // rdx
  unsigned int v8; // r12d
  __int64 v9; // rdi
  __int64 v10; // rax
  const WCHAR *v11; // rax
  __int64 v12; // rax
  __int64 v13; // r12
  const unsigned __int16 *SensorGroupPropertyName; // rdi
  const unsigned __int16 *v15; // rax
  DWORD v16; // esi
  size_t v17; // rdi
  unsigned __int8 *v18; // rax
  unsigned __int8 *v19; // r14
  const unsigned __int16 *v20; // rdi
  const unsigned __int16 *v21; // rax
  int v22; // eax
  __int64 v23; // rdx
  unsigned int *v25; // [rsp+28h] [rbp-40h]
  unsigned int *v26; // [rsp+28h] [rbp-40h]
  unsigned int v27; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkDeviceInterface; // [rsp+78h] [rbp+10h] BYREF
  __int64 v29; // [rsp+80h] [rbp+18h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v29 = 0;
  v5 = (char *)this - 8;
  v27 = 0;
  if ( a2 )
  {
    v8 = *((_DWORD *)v5 + 32);
    v6 = 0;
    v9 = 0;
    *a2 = GUID_00000000_0000_0000_0000_000000000000;
    while ( 1 )
    {
      if ( (unsigned int)v9 >= v8 )
        goto LABEL_22;
      v10 = *((_QWORD *)this + 14);
      phkDeviceInterface = 0;
      v11 = (const WCHAR *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 8 * v9) + 24LL))(*(_QWORD *)(v10 + 8 * v9));
      if ( !CM_Open_Device_Interface_KeyW(v11, 0x20019u, 1u, &phkDeviceInterface, 0) )
        break;
      v9 = (unsigned int)(v9 + 1);
    }
    _mm_lfence();
    RegCloseKey(phkDeviceInterface);
    v12 = *((_QWORD *)this + 14);
    phkDeviceInterface = 0;
    v13 = *(_QWORD *)(v12 + 8 * v9);
    if ( !v13 )
      goto LABEL_22;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 8LL))(*(_QWORD *)(v12 + 8 * v9));
    v29 = v13;
    SensorGroupPropertyName = GetSensorGroupPropertyName(0xAu);
    v15 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
    if ( (int)FSGetDeviceInterfaceRegistryEntry2(v15, SensorGroupPropertyName, 0, 0, &v27, v25) < 0 )
      goto LABEL_22;
    v16 = v27 + 2;
    v17 = v27 + 2;
    v18 = (unsigned __int8 *)operator new[](v17);
    v19 = v18;
    if ( !v18 )
    {
      v6 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_22;
      v7 = 146;
      goto LABEL_4;
    }
    memset_0(v18, 0, v17);
    v20 = GetSensorGroupPropertyName(0xAu);
    v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
    v22 = FSGetDeviceInterfaceRegistryEntry2(v21, v20, v19, v16, &v27, v26);
    v6 = v22;
    if ( v22 >= 0 )
    {
      v22 = IIDFromString((LPCOLESTR)v19, a2);
      v6 = v22;
      if ( v22 >= 0 || !g_wppLevels )
        goto LABEL_21;
      v23 = 148;
    }
    else
    {
      if ( !g_wppLevels )
      {
LABEL_21:
        operator delete(v19);
        goto LABEL_22;
      }
      v23 = 147;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v23, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, v5, v22);
    goto LABEL_21;
  }
  v6 = -2147467261;
  if ( g_wppLevels )
  {
    v7 = 145;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, v5, v6);
  }
LABEL_22:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v29);
  LeaveCriticalSection(v2);
  return v6;
}

```

## disassembly

```asm
0x18004fbb0  mov     [rsp+arg_18], rbx
0x18004fbb5  push    rbp
0x18004fbb6  push    rsi
0x18004fbb7  push    rdi
0x18004fbb8  push    r12
0x18004fbba  push    r13
0x18004fbbc  push    r14
0x18004fbbe  push    r15
0x18004fbc0  sub     rsp, 30h
0x18004fbc4  lea     rbx, [rcx+10h]
0x18004fbc8  mov     r14, rcx
0x18004fbcb  mov     rcx, rbx; lpCriticalSection
0x18004fbce  mov     r15, rdx
0x18004fbd1  call    cs:__imp_EnterCriticalSection
0x18004fbd7  mov     [rsp+68h+arg_10], 0
0x18004fbe3  lea     rbp, [r14-8]
0x18004fbe7  mov     [rsp+68h+arg_0], 0
0x18004fbef  test    r15, r15
0x18004fbf2  jnz     short loc_18004FC2E
0x18004fbf4  mov     esi, 80004003h
0x18004fbf9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004fc00  jb      loc_18004FDDF
0x18004fc06  mov     edx, 91h
0x18004fc0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fc12  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004fc19  mov     r9, rbp
0x18004fc1c  mov     [rsp+68h+ulFlags], esi
0x18004fc20  mov     rcx, [rcx+10h]
0x18004fc24  call    WPP_SF_qD
0x18004fc29  jmp     loc_18004FDDF
0x18004fc2e  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004fc35  mov     r12d, [rbp+80h]
0x18004fc3c  xor     esi, esi
0x18004fc3e  xor     edi, edi
0x18004fc40  movdqu  xmmword ptr [r15], xmm0
0x18004fc45  cmp     edi, r12d
0x18004fc48  jnb     loc_18004FDDF
0x18004fc4e  mov     rax, [r14+70h]
0x18004fc52  mov     [rsp+68h+phkDeviceInterface], rsi
0x18004fc57  mov     rcx, [rax+rdi*8]
0x18004fc5b  mov     rax, [rcx]
0x18004fc5e  mov     rax, [rax+18h]
0x18004fc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fc67  mov     rcx, rax; pszDeviceInterface
0x18004fc6a  mov     [rsp+68h+ulFlags], esi; ulFlags
0x18004fc6e  lea     r9, [rsp+68h+phkDeviceInterface]; phkDeviceInterface
0x18004fc73  mov     edx, 20019h; samDesired
0x18004fc78  mov     r8d, 1; Disposition
0x18004fc7e  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18004fc84  test    eax, eax
0x18004fc86  jz      short loc_18004FC8C
0x18004fc88  inc     edi
0x18004fc8a  jmp     short loc_18004FC45
0x18004fc8c  lfence
0x18004fc8f  mov     rcx, [rsp+68h+phkDeviceInterface]; hKey
0x18004fc94  call    cs:__imp_RegCloseKey
0x18004fc9a  mov     rax, [r14+70h]
0x18004fc9e  mov     [rsp+68h+phkDeviceInterface], rsi
0x18004fca3  mov     r12, [rax+rdi*8]
0x18004fca7  test    r12, r12
0x18004fcaa  jz      loc_18004FDDF
0x18004fcb0  mov     rax, [r12]
0x18004fcb4  mov     rcx, r12
0x18004fcb7  mov     rax, [rax+8]
0x18004fcbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fcc0  mov     r13d, 0Ah
0x18004fcc6  mov     [rsp+68h+arg_10], r12
0x18004fcce  mov     ecx, r13d; unsigned int
0x18004fcd1  call    ?GetSensorGroupPropertyName@@YAPEBGK@Z; GetSensorGroupPropertyName(ulong)
0x18004fcd6  mov     rdi, rax
0x18004fcd9  mov     rcx, r12
0x18004fcdc  mov     rax, [r12]
0x18004fce0  mov     rax, [rax+18h]
0x18004fce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fce9  lea     rcx, [rsp+68h+arg_0]
0x18004fcee  xor     r9d, r9d; unsigned int
0x18004fcf1  mov     qword ptr [rsp+68h+ulFlags], rcx; unsigned int *
0x18004fcf6  xor     r8d, r8d; unsigned __int8 *
0x18004fcf9  mov     rcx, rax; unsigned __int16 *
0x18004fcfc  mov     rdx, rdi; unsigned __int16 *
0x18004fcff  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x18004fd04  test    eax, eax
0x18004fd06  js      loc_18004FDDF
0x18004fd0c  mov     esi, [rsp+68h+arg_0]
0x18004fd10  add     esi, 2
0x18004fd13  mov     ecx, esi; unsigned __int64
0x18004fd15  mov     edi, esi
0x18004fd17  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004fd1c  mov     r14, rax
0x18004fd1f  test    rax, rax
0x18004fd22  jnz     short loc_18004FD40
0x18004fd24  mov     esi, 8007000Eh
0x18004fd29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004fd30  jb      loc_18004FDDF
0x18004fd36  mov     edx, 92h
0x18004fd3b  jmp     loc_18004FC0B
0x18004fd40  mov     r8, rdi; Size
0x18004fd43  xor     edx, edx; Val
0x18004fd45  mov     rcx, r14; void *
0x18004fd48  call    memset_0
0x18004fd4d  mov     ecx, r13d; unsigned int
0x18004fd50  call    ?GetSensorGroupPropertyName@@YAPEBGK@Z; GetSensorGroupPropertyName(ulong)
0x18004fd55  mov     rdi, rax
0x18004fd58  mov     rcx, r12
0x18004fd5b  mov     rax, [r12]
0x18004fd5f  mov     rax, [rax+18h]
0x18004fd63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fd68  lea     rcx, [rsp+68h+arg_0]
0x18004fd6d  mov     r9d, esi; unsigned int
0x18004fd70  mov     qword ptr [rsp+68h+ulFlags], rcx; unsigned int *
0x18004fd75  mov     r8, r14; unsigned __int8 *
0x18004fd78  mov     rcx, rax; unsigned __int16 *
0x18004fd7b  mov     rdx, rdi; unsigned __int16 *
0x18004fd7e  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x18004fd83  mov     esi, eax
0x18004fd85  test    eax, eax
0x18004fd87  jns     short loc_18004FD99
0x18004fd89  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004fd90  jb      short loc_18004FDD7
0x18004fd92  mov     edx, 93h
0x18004fd97  jmp     short loc_18004FDB9
0x18004fd99  mov     rdx, r15; lpiid
0x18004fd9c  mov     rcx, r14; lpsz
0x18004fd9f  call    cs:__imp_IIDFromString
0x18004fda5  mov     esi, eax
0x18004fda7  test    eax, eax
0x18004fda9  jns     short loc_18004FDD7
0x18004fdab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004fdb2  jb      short loc_18004FDD7
0x18004fdb4  mov     edx, 94h
0x18004fdb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fdc0  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004fdc7  mov     r9, rbp
0x18004fdca  mov     [rsp+68h+ulFlags], eax
0x18004fdce  mov     rcx, [rcx+10h]
0x18004fdd2  call    WPP_SF_qD
0x18004fdd7  mov     rcx, r14; Block
0x18004fdda  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004fddf  lea     rcx, [rsp+68h+arg_10]
0x18004fde7  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004fdec  mov     rcx, rbx; lpCriticalSection
0x18004fdef  call    cs:__imp_LeaveCriticalSection
0x18004fdf5  mov     rbx, [rsp+68h+arg_18]
0x18004fdfd  mov     eax, esi
0x18004fdff  add     rsp, 30h
0x18004fe03  pop     r15
0x18004fe05  pop     r14
0x18004fe07  pop     r13
0x18004fe09  pop     r12
0x18004fe0b  pop     rdi
0x18004fe0c  pop     rsi
0x18004fe0d  pop     rbp
0x18004fe0e  retn
```
