# Broker::DeviceInterfaceArrivalEvent::IsDeviceHwidPresentOnPath(ushort const *)

- ea: `0x180011e10`
- end: `0x180012438`
- name: `?IsDeviceHwidPresentOnPath@DeviceInterfaceArrivalEvent@Broker@@AEAA_NPEBG@Z`
- size: `1576`
- prototype: `char __fastcall(Broker::DeviceInterfaceArrivalEvent *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011d60`
- `0x180019170`

## callees

- `0x18000b168`
- `0x180011e10`
- `0x180019130`
- `0x180019224`
- `0x1800193c4`
- `0x18001d364`
- `0x18001d9a0`
- `0x18001d9ac`
- `0x18001e0d8`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180011f29`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180011fae`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180011f29`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x180011fae`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180011eb1`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180011eb1`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180011e98`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180011e98`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
char __fastcall Broker::DeviceInterfaceArrivalEvent::IsDeviceHwidPresentOnPath(
        Broker::DeviceInterfaceArrivalEvent *this,
        const unsigned __int16 *a2)
{
  char *v4; // rsi
  unsigned __int64 v5; // rdx
  PBYTE v6; // rax
  CONFIGRET Device_Interface_PropertyW; // eax
  DEVNODE v8; // edi
  char *v9; // rsi
  unsigned __int64 v10; // rcx
  PBYTE v11; // rax
  void *v12; // rcx
  DEVNODE v13; // esi
  char *v14; // rdi
  unsigned __int64 v15; // rcx
  PBYTE v16; // rax
  void *v17; // rcx
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // r12
  const wchar_t *v21; // rsi
  __int64 v22; // r14
  __int64 i; // rbx
  unsigned __int64 v24; // rdi
  unsigned __int64 v25; // r15
  const wchar_t *v26; // rcx
  size_t v27; // r8
  char v28; // bl
  PBYTE v29; // rcx
  unsigned __int64 v30; // rax
  unsigned __int64 v31; // r12
  const wchar_t *v32; // rsi
  __int64 v33; // r14
  __int64 j; // rbx
  unsigned __int64 v35; // rdi
  unsigned __int64 v36; // r15
  const wchar_t *v37; // rcx
  size_t v38; // r8
  char v39; // bl
  size_t v40; // rbx
  size_t v41; // rbx
  size_t v42; // rbx
  DEVPROPTYPE v43[2]; // [rsp+30h] [rbp-39h] BYREF
  DEVPROPTYPE v44; // [rsp+38h] [rbp-31h] BYREF
  PBYTE pExceptionObject; // [rsp+40h] [rbp-29h] BYREF
  void *v46[2]; // [rsp+48h] [rbp-21h]
  int v47; // [rsp+58h] [rbp-11h]
  CONFIGRET v48; // [rsp+60h] [rbp-9h]
  void *v49; // [rsp+68h] [rbp-1h] BYREF
  PBYTE PropertyBuffer; // [rsp+70h] [rbp+7h] BYREF
  void *v51; // [rsp+78h] [rbp+Fh]
  __int64 v52; // [rsp+80h] [rbp+17h]
  ULONG PropertyBufferSize; // [rsp+88h] [rbp+1Fh] BYREF
  DEVPROPTYPE PropertyType[13]; // [rsp+8Ch] [rbp+23h] BYREF
  DEVNODE pdnDevInst; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 v56; // [rsp+E8h] [rbp+7Fh] BYREF

  pdnDevInst = 0;
  PropertyType[0] = 0;
  std::vector<_GUID>::vector<_GUID>(&PropertyBuffer);
  PropertyBufferSize = 2048;
  v4 = (char *)v51;
  v5 = ((_BYTE *)v51 - PropertyBuffer) >> 1;
  if ( v5 > 0x400 )
  {
    v6 = PropertyBuffer + 2048;
LABEL_3:
    v51 = v6;
    goto LABEL_4;
  }
  if ( v5 < 0x400 )
  {
    if ( (unsigned __int64)((v52 - (__int64)PropertyBuffer) >> 1) >= 0x400 )
    {
      v40 = 2 * (1024 - v5);
      memset_0(v51, 0, v40);
      v6 = (PBYTE)&v4[v40];
      goto LABEL_3;
    }
    std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&PropertyBuffer, 1024);
  }
LABEL_4:
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 a2,
                                 &DEVPKEY_Device_InstanceId,
                                 PropertyType,
                                 PropertyBuffer,
                                 &PropertyBufferSize,
                                 0);
  if ( Device_Interface_PropertyW )
  {
    *(_OWORD *)v46 = 0;
    v47 = 1;
    pExceptionObject = (PBYTE)&Broker::Win32Error::`vftable';
    v48 = Device_Interface_PropertyW;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  if ( CM_Locate_DevNodeW(&pdnDevInst, (DEVINSTID_W)PropertyBuffer, 0) )
  {
    v17 = PropertyBuffer;
    if ( !PropertyBuffer )
      return 0;
    v56 = 2 * ((v52 - (__int64)PropertyBuffer) >> 1);
    *(_QWORD *)v43 = PropertyBuffer;
    if ( v56 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned((void **)v43, &v56);
      v17 = *(void **)v43;
    }
    goto LABEL_79;
  }
  v8 = pdnDevInst;
  v44 = 0;
  std::vector<_GUID>::vector<_GUID>(&pExceptionObject);
  if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 7) )
  {
    if ( pExceptionObject )
      std::_Deallocate<16>(pExceptionObject, 2 * (((char *)v46[1] - (char *)pExceptionObject) >> 1));
    goto LABEL_49;
  }
  LODWORD(v56) = 2048;
  v9 = (char *)v46[0];
  v10 = ((char *)v46[0] - (char *)pExceptionObject) >> 1;
  if ( v10 <= 0x400 )
  {
    if ( v10 >= 0x400 )
      goto LABEL_10;
    if ( (unsigned __int64)(((char *)v46[1] - (char *)pExceptionObject) >> 1) < 0x400 )
    {
      std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&pExceptionObject, 1024);
      goto LABEL_10;
    }
    v41 = 2 * (1024 - v10);
    memset_0(v46[0], 0, v41);
    v11 = (PBYTE)&v9[v41];
  }
  else
  {
    v11 = pExceptionObject + 2048;
  }
  v46[0] = v11;
LABEL_10:
  if ( CM_Get_DevNode_PropertyW(v8, &DEVPKEY_Device_HardwareIds, &v44, pExceptionObject, (PULONG)&v56, 0) )
  {
    v12 = pExceptionObject;
    if ( pExceptionObject )
    {
      *(_QWORD *)v43 = 2 * (((char *)v46[1] - (char *)pExceptionObject) >> 1);
      v49 = pExceptionObject;
      if ( *(_QWORD *)v43 >= 0x1000u )
      {
        std::_Adjust_manually_vector_aligned(&v49, (unsigned __int64 *)v43);
        v12 = v49;
      }
      operator delete(v12);
    }
    goto LABEL_12;
  }
  v19 = (unsigned int)v56 >> 1;
  v43[0] = (unsigned int)v56 >> 1;
  v20 = 0;
  v21 = (const wchar_t *)pExceptionObject;
  v22 = -1;
  do
    ++v22;
  while ( *(_WORD *)&pExceptionObject[2 * v22] );
  while ( v22 && v20 < v19 )
  {
    for ( i = *((_QWORD *)this + 7); i != *((_QWORD *)this + 8); i += 32 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v21[v24] );
      v25 = *(_QWORD *)(i + 16);
      if ( *(_QWORD *)(i + 24) <= 7u )
        v26 = (const wchar_t *)i;
      else
        v26 = *(const wchar_t **)i;
      v27 = *(_QWORD *)(i + 16);
      if ( v24 < v25 )
        v27 = v24;
      if ( !wmemcmp(v26, v21, v27) && v25 >= v24 && v25 <= v24 )
      {
        v28 = 1;
        goto LABEL_46;
      }
    }
    v20 += v22 + 1;
    v21 += v22 + 1;
    v22 = -1;
    do
      ++v22;
    while ( v21[v22] );
    v19 = v43[0];
  }
  v28 = 0;
LABEL_46:
  if ( pExceptionObject )
    std::_Deallocate<16>(pExceptionObject, 2 * (((char *)v46[1] - (char *)pExceptionObject) >> 1));
  if ( !v28 )
  {
LABEL_12:
    v13 = pdnDevInst;
    v43[0] = 0;
    std::vector<_GUID>::vector<_GUID>(&pExceptionObject);
    if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 7) )
    {
      if ( pExceptionObject )
        std::_Deallocate<16>(pExceptionObject, 2 * (((char *)v46[1] - (char *)pExceptionObject) >> 1));
      goto LABEL_84;
    }
    LODWORD(v56) = 2048;
    v14 = (char *)v46[0];
    v15 = ((char *)v46[0] - (char *)pExceptionObject) >> 1;
    if ( v15 <= 0x400 )
    {
      if ( v15 >= 0x400 )
        goto LABEL_16;
      if ( (unsigned __int64)(((char *)v46[1] - (char *)pExceptionObject) >> 1) < 0x400 )
      {
        std::vector<unsigned short>::_Resize_reallocate<std::_Value_init_tag>(&pExceptionObject, 1024);
        goto LABEL_16;
      }
      v42 = 2 * (1024 - v15);
      memset_0(v46[0], 0, v42);
      v16 = (PBYTE)&v14[v42];
    }
    else
    {
      v16 = pExceptionObject + 2048;
    }
    v46[0] = v16;
LABEL_16:
    if ( CM_Get_DevNode_PropertyW(v13, &DEVPKEY_Device_CompatibleIds, v43, pExceptionObject, (PULONG)&v56, 0) )
    {
      if ( pExceptionObject )
        std::_Deallocate<16>(pExceptionObject, 2 * (((char *)v46[1] - (char *)pExceptionObject) >> 1));
LABEL_19:
      v17 = PropertyBuffer;
      if ( !PropertyBuffer )
        return 0;
      v56 = 2 * ((v52 - (__int64)PropertyBuffer) >> 1);
      v49 = PropertyBuffer;
      if ( v56 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v49, &v56);
        v17 = v49;
      }
LABEL_79:
      operator delete(v17);
      return 0;
    }
    v30 = (unsigned int)v56 >> 1;
    v44 = (unsigned int)v56 >> 1;
    v31 = 0;
    v32 = (const wchar_t *)pExceptionObject;
    v33 = -1;
    do
      ++v33;
    while ( *(_WORD *)&pExceptionObject[2 * v33] );
    while ( v33 && v31 < v30 )
    {
      for ( j = *((_QWORD *)this + 7); j != *((_QWORD *)this + 8); j += 32 )
      {
        v35 = -1;
        do
          ++v35;
        while ( v32[v35] );
        v36 = *(_QWORD *)(j + 16);
        if ( *(_QWORD *)(j + 24) <= 7u )
          v37 = (const wchar_t *)j;
        else
          v37 = *(const wchar_t **)j;
        v38 = *(_QWORD *)(j + 16);
        if ( v35 < v36 )
          v38 = v35;
        if ( !wmemcmp(v37, v32, v38) && v36 >= v35 && v36 <= v35 )
        {
          v39 = 1;
          goto LABEL_73;
        }
      }
      v31 += v33 + 1;
      v32 += v33 + 1;
      v33 = -1;
      do
        ++v33;
      while ( v32[v33] );
      v30 = v44;
    }
    v39 = 0;
LABEL_73:
    if ( pExceptionObject )
      std::_Deallocate<16>(pExceptionObject, 2 * (((char *)v46[1] - (char *)pExceptionObject) >> 1));
    if ( !v39 )
      goto LABEL_19;
LABEL_84:
    v29 = PropertyBuffer;
    if ( PropertyBuffer )
      goto LABEL_85;
    return 1;
  }
LABEL_49:
  v29 = PropertyBuffer;
  if ( PropertyBuffer )
LABEL_85:
    std::_Deallocate<16>(v29, 2 * ((v52 - (__int64)v29) >> 1));
  return 1;
}

```

## disassembly

```asm
0x180011e10  mov     [rsp-8+arg_0], rbx
0x180011e15  push    rbp
0x180011e16  push    rsi
0x180011e17  push    rdi
0x180011e18  push    r12
0x180011e1a  push    r13
0x180011e1c  push    r14
0x180011e1e  push    r15
0x180011e20  lea     rbp, [rsp-27h]
0x180011e25  sub     rsp, 90h
0x180011e2c  mov     rdi, rdx
0x180011e2f  mov     r13, rcx
0x180011e32  xor     r15d, r15d
0x180011e35  mov     [rbp+57h+pdnDevInst], r15d
0x180011e39  mov     [rbp+57h+PropertyType], r15d
0x180011e3d  lea     rcx, [rbp+57h+PropertyBuffer]
0x180011e41  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180011e46  nop
0x180011e47  mov     [rbp+57h+var_38], 800h
0x180011e4e  mov     r8, [rbp+57h+PropertyBuffer]
0x180011e52  mov     rsi, [rbp+57h+var_48]
0x180011e56  mov     rdx, rsi
0x180011e59  sub     rdx, r8
0x180011e5c  sar     rdx, 1
0x180011e5f  mov     ebx, 400h
0x180011e64  cmp     rdx, rbx
0x180011e67  jbe     loc_1800122FF
0x180011e6d  lea     rax, [r8+800h]
0x180011e74  mov     [rbp+57h+var_48], rax
0x180011e78  mov     [rsp+0C0h+ulFlags], r15d; ulFlags
0x180011e7d  lea     rax, [rbp+57h+var_38]
0x180011e81  mov     [rsp+0C0h+PropertyBufferSize], rax; PropertyBufferSize
0x180011e86  mov     r9, [rbp+57h+PropertyBuffer]; PropertyBuffer
0x180011e8a  lea     r8, [rbp+57h+PropertyType]; PropertyType
0x180011e8e  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x180011e95  mov     rcx, rdi; pszDeviceInterface
0x180011e98  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180011e9e  test    eax, eax
0x180011ea0  jnz     loc_18001234A
0x180011ea6  xor     r8d, r8d; ulFlags
0x180011ea9  mov     rdx, [rbp+57h+PropertyBuffer]; pDeviceID
0x180011ead  lea     rcx, [rbp+57h+pdnDevInst]; pdnDevInst
0x180011eb1  call    cs:__imp_CM_Locate_DevNodeW
0x180011eb7  test    eax, eax
0x180011eb9  jnz     loc_180011FF3
0x180011ebf  mov     edi, [rbp+57h+pdnDevInst]
0x180011ec2  mov     [rbp+57h+var_88], r15d
0x180011ec6  lea     rcx, [rbp+57h+pExceptionObject]
0x180011eca  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180011ecf  nop
0x180011ed0  mov     rax, [r13+40h]
0x180011ed4  cmp     rax, [r13+38h]
0x180011ed8  jz      loc_1800122CD
0x180011ede  mov     dword ptr [rbp+57h+arg_18], 800h
0x180011ee5  mov     rdx, [rbp+57h+pExceptionObject]
0x180011ee9  mov     rsi, [rbp+57h+var_78]
0x180011eed  mov     rcx, rsi
0x180011ef0  sub     rcx, rdx
0x180011ef3  sar     rcx, 1
0x180011ef6  cmp     rcx, rbx
0x180011ef9  jbe     loc_180012377
0x180011eff  lea     rax, [rdx+800h]
0x180011f06  mov     [rbp+57h+var_78], rax
0x180011f0a  mov     [rsp+0C0h+ulFlags], r15d; ulFlags
0x180011f0f  lea     rax, [rbp+57h+arg_18]
0x180011f13  mov     [rsp+0C0h+PropertyBufferSize], rax; PropertyBufferSize
0x180011f18  mov     r9, [rbp+57h+pExceptionObject]; PropertyBuffer
0x180011f1c  lea     r8, [rbp+57h+var_88]; PropertyType
0x180011f20  lea     rdx, DEVPKEY_Device_HardwareIds; PropertyKey
0x180011f27  mov     ecx, edi; dnDevInst
0x180011f29  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180011f2f  test    eax, eax
0x180011f31  jz      loc_180012034
0x180011f37  mov     rcx, [rbp+57h+pExceptionObject]; void *
0x180011f3b  test    rcx, rcx
0x180011f3e  jnz     loc_180012218
0x180011f44  mov     esi, [rbp+57h+pdnDevInst]
0x180011f47  mov     [rbp+57h+var_90], r15d
0x180011f4b  lea     rcx, [rbp+57h+pExceptionObject]
0x180011f4f  call    ??0?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAA@XZ; std::vector<_GUID>::vector<_GUID>(void)
0x180011f54  nop
0x180011f55  mov     rax, [r13+40h]
0x180011f59  cmp     rax, [r13+38h]
0x180011f5d  jz      loc_1800122F1
0x180011f63  mov     dword ptr [rbp+57h+arg_18], 800h
0x180011f6a  mov     rdx, [rbp+57h+pExceptionObject]
0x180011f6e  mov     rdi, [rbp+57h+var_78]
0x180011f72  mov     rcx, rdi
0x180011f75  sub     rcx, rdx
0x180011f78  sar     rcx, 1
0x180011f7b  cmp     rcx, rbx
0x180011f7e  jbe     loc_1800123DC
0x180011f84  lea     rax, [rdx+800h]
0x180011f8b  mov     [rbp+57h+var_78], rax
0x180011f8f  mov     [rsp+0C0h+ulFlags], r15d; ulFlags
0x180011f94  lea     rax, [rbp+57h+arg_18]
0x180011f98  mov     [rsp+0C0h+PropertyBufferSize], rax; PropertyBufferSize
0x180011f9d  mov     r9, [rbp+57h+pExceptionObject]; PropertyBuffer
0x180011fa1  lea     r8, [rbp+57h+var_90]; PropertyType
0x180011fa5  lea     rdx, DEVPKEY_Device_CompatibleIds; PropertyKey
0x180011fac  mov     ecx, esi; dnDevInst
0x180011fae  call    cs:__imp_CM_Get_DevNode_PropertyW
0x180011fb4  test    eax, eax
0x180011fb6  jz      loc_18001211B
0x180011fbc  mov     rcx, [rbp+57h+pExceptionObject]
0x180011fc0  test    rcx, rcx
0x180011fc3  jnz     loc_180012244
0x180011fc9  mov     rcx, [rbp+57h+PropertyBuffer]; void *
0x180011fcd  test    rcx, rcx
0x180011fd0  jnz     loc_1800121EC
0x180011fd6  xor     al, al
0x180011fd8  mov     rbx, [rsp+0C0h+arg_0]
0x180011fe0  add     rsp, 90h
0x180011fe7  pop     r15
0x180011fe9  pop     r14
0x180011feb  pop     r13
0x180011fed  pop     r12
0x180011fef  pop     rdi
0x180011ff0  pop     rsi
0x180011ff1  pop     rbp
0x180011ff2  retn
0x180011ff3  mov     rcx, [rbp+57h+PropertyBuffer]
0x180011ff7  test    rcx, rcx
0x180011ffa  jz      short loc_180011FD6
0x180011ffc  mov     rdx, [rbp+57h+var_40]
0x180012000  sub     rdx, rcx
0x180012003  sar     rdx, 1
0x180012006  add     rdx, rdx
0x180012009  mov     [rbp+57h+arg_18], rdx
0x18001200d  mov     qword ptr [rbp+57h+var_90], rcx
0x180012011  cmp     rdx, 1000h
0x180012018  jb      loc_18001220E
0x18001201e  lea     rdx, [rbp+57h+arg_18]; unsigned __int64 *
0x180012022  lea     rcx, [rbp+57h+var_90]; void **
0x180012026  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18001202b  mov     rcx, qword ptr [rbp+57h+var_90]
0x18001202f  jmp     loc_18001242F
0x180012034  mov     eax, dword ptr [rbp+57h+arg_18]
0x180012037  shr     eax, 1
0x180012039  mov     [rbp+57h+var_90], eax
0x18001203c  mov     r12, r15
0x18001203f  mov     rsi, [rbp+57h+pExceptionObject]
0x180012043  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18001204a  nop     word ptr [rax+rax+00h]
0x180012050  inc     r14
0x180012053  cmp     [rsi+r14*2], r12w
0x180012058  jnz     short loc_180012050
0x18001205a  nop     word ptr [rax+rax+00h]
0x180012060  test    r14, r14
0x180012063  jz      loc_1800120F0
0x180012069  cmp     r12, rax
0x18001206c  jnb     loc_1800120F0
0x180012072  mov     rbx, [r13+38h]
0x180012076  cmp     rbx, [r13+40h]
0x18001207a  jz      short loc_1800120B7
0x18001207c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180012083  inc     rdi
0x180012086  cmp     word ptr [rsi+rdi*2], 0
0x18001208b  jnz     short loc_180012083
0x18001208d  mov     r15, [rbx+10h]
0x180012091  cmp     qword ptr [rbx+18h], 7
0x180012096  jbe     short loc_1800120E0
0x180012098  mov     rcx, [rbx]; S1
0x18001209b  mov     r8, r15
0x18001209e  cmp     rdi, r15
0x1800120a1  cmovb   r8, rdi; N
0x1800120a5  mov     rdx, rsi; S2
0x1800120a8  call    wmemcmp
0x1800120ad  test    eax, eax
0x1800120af  jz      short loc_1800120E5
0x1800120b1  add     rbx, 20h ; ' '
0x1800120b5  jmp     short loc_180012076
0x1800120b7  inc     r12
0x1800120ba  add     r12, r14
0x1800120bd  lea     rsi, [rsi+r14*2]
0x1800120c1  add     rsi, 2
0x1800120c5  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800120cc  nop     dword ptr [rax+00h]
0x1800120d0  inc     r14
0x1800120d3  cmp     word ptr [rsi+r14*2], 0
0x1800120d9  jnz     short loc_1800120D0
0x1800120db  mov     eax, [rbp+57h+var_90]
0x1800120de  jmp     short loc_180012060
0x1800120e0  mov     rcx, rbx
0x1800120e3  jmp     short loc_18001209B
0x1800120e5  cmp     r15, rdi
0x1800120e8  jb      short loc_1800120B1
0x1800120ea  ja      short loc_1800120B1
0x1800120ec  mov     bl, 1
0x1800120ee  jmp     short loc_1800120F2
0x1800120f0  xor     bl, bl
0x1800120f2  mov     rcx, [rbp+57h+pExceptionObject]
0x1800120f6  test    rcx, rcx
0x1800120f9  jnz     loc_18001229F
0x1800120ff  test    bl, bl
0x180012101  jz      loc_18001225B
0x180012107  mov     rcx, [rbp+57h+PropertyBuffer]
0x18001210b  test    rcx, rcx
0x18001210e  jnz     loc_180012288
0x180012114  mov     al, 1
0x180012116  jmp     loc_180011FD8
0x18001211b  mov     eax, dword ptr [rbp+57h+arg_18]
0x18001211e  shr     eax, 1
0x180012120  mov     [rbp+57h+var_88], eax
0x180012123  mov     r12, r15
0x180012126  mov     rsi, [rbp+57h+pExceptionObject]
0x18001212a  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180012131  inc     r14
0x180012134  cmp     word ptr [rsi+r14*2], 0
0x18001213a  jnz     short loc_180012131
0x18001213c  nop     dword ptr [rax+00h]
0x180012140  test    r14, r14
0x180012143  jz      loc_1800121D0
0x180012149  cmp     r12, rax
0x18001214c  jnb     loc_1800121D0
0x180012152  mov     rbx, [r13+38h]
0x180012156  cmp     rbx, [r13+40h]
0x18001215a  jz      short loc_180012197
0x18001215c  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180012163  inc     rdi
0x180012166  cmp     word ptr [rsi+rdi*2], 0
0x18001216b  jnz     short loc_180012163
0x18001216d  mov     r15, [rbx+10h]
0x180012171  cmp     qword ptr [rbx+18h], 7
0x180012176  jbe     short loc_1800121C0
0x180012178  mov     rcx, [rbx]; S1
0x18001217b  mov     r8, r15
0x18001217e  cmp     rdi, r15
0x180012181  cmovb   r8, rdi; N
0x180012185  mov     rdx, rsi; S2
0x180012188  call    wmemcmp
0x18001218d  test    eax, eax
0x18001218f  jz      short loc_1800121C5
0x180012191  add     rbx, 20h ; ' '
0x180012195  jmp     short loc_180012156
0x180012197  inc     r12
0x18001219a  add     r12, r14
0x18001219d  lea     rsi, [rsi+r14*2]
0x1800121a1  add     rsi, 2
0x1800121a5  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800121ac  nop     dword ptr [rax+00h]
0x1800121b0  inc     r14
0x1800121b3  cmp     word ptr [rsi+r14*2], 0
0x1800121b9  jnz     short loc_1800121B0
0x1800121bb  mov     eax, [rbp+57h+var_88]
0x1800121be  jmp     short loc_180012140
0x1800121c0  mov     rcx, rbx
0x1800121c3  jmp     short loc_18001217B
0x1800121c5  cmp     r15, rdi
0x1800121c8  jb      short loc_180012191
0x1800121ca  ja      short loc_180012191
0x1800121cc  mov     bl, 1
0x1800121ce  jmp     short loc_1800121D2
0x1800121d0  xor     bl, bl
0x1800121d2  mov     rcx, [rbp+57h+pExceptionObject]
0x1800121d6  test    rcx, rcx
0x1800121d9  jnz     loc_1800122B6
0x1800121df  test    bl, bl
0x1800121e1  jz      loc_180011FC9
0x1800121e7  jmp     loc_18001227B
0x1800121ec  mov     rdx, [rbp+57h+var_40]
0x1800121f0  sub     rdx, rcx
0x1800121f3  sar     rdx, 1
0x1800121f6  add     rdx, rdx; unsigned __int64
0x1800121f9  mov     [rbp+57h+arg_18], rdx
0x1800121fd  mov     [rbp+57h+var_58], rcx
0x180012201  cmp     rdx, 1000h
0x180012208  jnb     loc_18001241E
0x18001220e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012213  jmp     loc_180011FD6
0x180012218  mov     rdx, [rbp+57h+var_78+8]
0x18001221c  sub     rdx, rcx
0x18001221f  sar     rdx, 1
0x180012222  add     rdx, rdx; unsigned __int64
0x180012225  mov     qword ptr [rbp+57h+var_90], rdx
0x180012229  mov     [rbp+57h+var_58], rcx
0x18001222d  cmp     rdx, 1000h
0x180012234  jnb     loc_1800123C2
0x18001223a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001223f  jmp     loc_180011F44
0x180012244  mov     rdx, [rbp+57h+var_78+8]
0x180012248  sub     rdx, rcx
0x18001224b  sar     rdx, 1
0x18001224e  add     rdx, rdx
0x180012251  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180012256  jmp     loc_180011FC9
0x18001225b  mov     ebx, 400h
0x180012260  xor     r15d, r15d
0x180012263  jmp     loc_180011F44
0x180012268  mov     rdx, [rbp+57h+var_78+8]
0x18001226c  sub     rdx, rcx
0x18001226f  sar     rdx, 1
0x180012272  add     rdx, rdx
0x180012275  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001227a  nop
0x18001227b  mov     rcx, [rbp+57h+PropertyBuffer]
0x18001227f  test    rcx, rcx
0x180012282  jz      loc_180012114
0x180012288  mov     rdx, [rbp+57h+var_40]
0x18001228c  sub     rdx, rcx
  ... truncated ...
```
