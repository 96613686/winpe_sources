# EvtGetChannelConfigProperty

- ea: `0x1800106b0`
- end: `0x180010837`
- name: `EvtGetChannelConfigProperty`
- size: `391`
- prototype: `BOOL __stdcall(EVT_HANDLE ChannelConfig, EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId, DWORD Flags, DWORD PropertyValueBufferSize, PEVT_VARIANT PropertyValueBuffer, PDWORD PropertyValueBufferUsed)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180006870`
- `0x180006aec`
- `0x1800106b0`
- `0x1800108d0`
- `0x1800109c0`
- `0x180023548`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001076e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001076e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall EvtGetChannelConfigProperty(
        EVT_HANDLE ChannelConfig,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId,
        DWORD Flags,
        DWORD PropertyValueBufferSize,
        PEVT_VARIANT PropertyValueBuffer,
        PDWORD PropertyValueBufferUsed)
{
  __int64 v10; // rcx
  BOOL v11; // edi
  DWORD ReferencedObject; // esi
  ChannelConfigObject *v13; // rbx
  wmi::RefBase *v15; // [rsp+30h] [rbp-68h] BYREF
  wmi::RefBase *v16; // [rsp+38h] [rbp-60h]
  EvtException *v17; // [rsp+40h] [rbp-58h] BYREF
  __int128 pExceptionObject; // [rsp+48h] [rbp-50h] BYREF
  __int64 v19; // [rsp+58h] [rbp-40h]
  int v20; // [rsp+60h] [rbp-38h]
  int v21; // [rsp+64h] [rbp-34h]
  int v22; // [rsp+68h] [rbp-30h]

  LastErrInfo::Reset((LastErrInfo *)ChannelConfig);
  try
  {
    v11 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v19 = 0;
      v20 = 87;
      v21 = -1;
      v22 = 1566;
      throw (EvtException *)&pExceptionObject;
    }
    if ( PropertyValueBufferSize && !PropertyValueBuffer || !PropertyValueBufferUsed )
    {
      ReferencedObject = 87;
      goto LABEL_28;
    }
    v13 = 0;
    v16 = 0;
    v15 = 0;
    ReferencedObject = ObjectTable::GetReferencedObject(v10, ChannelConfig, &v15);
    if ( !ReferencedObject )
    {
      if ( *((_BYTE *)v15 + 28) == 10 )
      {
        v13 = v15;
        v16 = v15;
        if ( v15 )
        {
          ReferencedObject = 0;
LABEL_11:
          if ( !ReferencedObject )
            ReferencedObject = ChannelConfigObject::GetProperty(
                                 v13,
                                 PropertyId,
                                 PropertyValueBufferSize,
                                 PropertyValueBuffer,
                                 PropertyValueBufferUsed);
          goto LABEL_13;
        }
      }
      else
      {
        v13 = 0;
      }
      wmi::RefBase::Release(v15);
      ReferencedObject = 6;
LABEL_13:
      if ( v13 )
        wmi::RefBase::Release(v13);
      goto LABEL_28;
    }
    if ( v15 )
      wmi::RefBase::Release(v15);
    goto LABEL_11;
  }
  catch ( EvtException *v17 )
  {
    v11 = 0;
    ReferencedObject = *((_DWORD *)v17 + 6);
  }
LABEL_28:
  SetLastError(ReferencedObject);
  LOBYTE(v11) = ReferencedObject == 0;
  return v11;
}

```

## disassembly

```asm
0x1800106b0  mov     [rsp+arg_0], rbx
0x1800106b5  mov     [rsp+arg_8], rsi
0x1800106ba  push    rdi
0x1800106bb  push    r12
0x1800106bd  push    r13
0x1800106bf  push    r14
0x1800106c1  push    r15
0x1800106c3  sub     rsp, 70h
0x1800106c7  mov     r12d, r9d
0x1800106ca  mov     ebx, r8d
0x1800106cd  mov     r13d, edx
0x1800106d0  mov     rsi, rcx
0x1800106d3  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x1800106d8  xor     edi, edi
0x1800106da  test    ebx, ebx
0x1800106dc  jnz     loc_1800107B4
0x1800106e2  mov     r14, [rsp+98h+PropertyValueBuffer]
0x1800106ea  test    r12d, r12d
0x1800106ed  jz      short loc_1800106FB
0x1800106ef  test    r14, r14
0x1800106f2  jnz     short loc_1800106FB
0x1800106f4  mov     esi, 57h ; 'W'
0x1800106f9  jmp     short loc_18001076C
0x1800106fb  mov     r15, [rsp+98h+PropertyValueBufferUsed]
0x180010703  test    r15, r15
0x180010706  jz      short loc_1800106F4
0x180010708  mov     rbx, rdi
0x18001070b  mov     [rsp+98h+var_60], rbx
0x180010710  mov     [rsp+98h+var_68], rdi
0x180010715  lea     r8, [rsp+98h+var_68]
0x18001071a  mov     rdx, rsi
0x18001071d  call    ?GetReferencedObject@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VObject@@@wmi@@@Z; ObjectTable::GetReferencedObject(void *,wmi::AutoRef<Object> &)
0x180010722  mov     esi, eax
0x180010724  mov     rcx, [rsp+98h+var_68]; this
0x180010729  test    eax, eax
0x18001072b  jnz     short loc_1800107A8
0x18001072d  cmp     byte ptr [rcx+1Ch], 0Ah
0x180010731  jnz     short loc_1800107A3
0x180010733  mov     rbx, rcx
0x180010736  mov     [rsp+98h+var_60], rcx
0x18001073b  test    rcx, rcx
0x18001073e  jz      short loc_180010796
0x180010740  mov     esi, edi
0x180010742  test    esi, esi
0x180010744  jnz     short loc_18001075E
0x180010746  mov     [rsp+98h+var_78], r15; unsigned int *
0x18001074b  mov     r9, r14; struct _EVT_VARIANT *
0x18001074e  mov     r8d, r12d; unsigned int
0x180010751  mov     edx, r13d; unsigned int
0x180010754  mov     rcx, rbx; this
0x180010757  call    ?GetProperty@ChannelConfigObject@@UEAAKKKPEAU_EVT_VARIANT@@AEAK@Z; ChannelConfigObject::GetProperty(ulong,ulong,_EVT_VARIANT *,ulong &)
0x18001075c  mov     esi, eax
0x18001075e  test    rbx, rbx
0x180010761  jz      short loc_18001076C
0x180010763  mov     rcx, rbx; this
0x180010766  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001076b  nop
0x18001076c  mov     ecx, esi; dwErrCode
0x18001076e  call    cs:__imp_SetLastError
0x180010774  test    esi, esi
0x180010776  setz    dil
0x18001077a  mov     eax, edi
0x18001077c  lea     r11, [rsp+98h+var_28]
0x180010781  mov     rbx, [r11+30h]
0x180010785  mov     rsi, [r11+38h]
0x180010789  mov     rsp, r11
0x18001078c  pop     r15
0x18001078e  pop     r14
0x180010790  pop     r13
0x180010792  pop     r12
0x180010794  pop     rdi
0x180010795  retn
0x180010796  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18001079b  nop
0x18001079c  mov     esi, 6
0x1800107a1  jmp     short loc_18001075E
0x1800107a3  mov     rbx, rdi
0x1800107a6  jmp     short loc_180010796
0x1800107a8  test    rcx, rcx
0x1800107ab  jz      short loc_180010742
0x1800107ad  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x1800107b2  jmp     short loc_180010742
0x1800107b4  lea     rax, WPP_GLOBAL_Control
0x1800107bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107c2  cmp     rcx, rax
0x1800107c5  jz      short loc_1800107F0
0x1800107c7  test    byte ptr [rcx+1Ch], 1
0x1800107cb  jz      short loc_1800107F0
0x1800107cd  cmp     byte ptr [rcx+19h], 2
0x1800107d1  jb      short loc_1800107F0
0x1800107d3  mov     edx, 30h ; '0'
0x1800107d8  lea     esi, [rdx+27h]
0x1800107db  mov     r9d, esi
0x1800107de  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800107e5  mov     rcx, [rcx+10h]
0x1800107e9  call    WPP_SF_D
0x1800107ee  jmp     short loc_1800107F5
0x1800107f0  mov     esi, 57h ; 'W'
0x1800107f5  xorps   xmm0, xmm0
0x1800107f8  movdqu  [rsp+98h+pExceptionObject], xmm0
0x1800107fe  mov     [rsp+98h+var_40], rdi
0x180010803  mov     [rsp+98h+var_38], esi
0x180010807  mov     [rsp+98h+var_34], 0FFFFFFFFh
0x18001080f  mov     [rsp+98h+var_30], 61Eh
0x180010817  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18001081e  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x180010823  call    _CxxThrowException_0
0x180010829  xor     edi, edi
0x18001082b  mov     esi, [rsp+98h+arg_10]
0x180010832  jmp     loc_18001076C
```
