# EvtSetChannelConfigProperty

- ea: `0x180026450`
- end: `0x18002656a`
- name: `EvtSetChannelConfigProperty`
- size: `282`
- prototype: `BOOL __stdcall(EVT_HANDLE ChannelConfig, EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId, DWORD Flags, PEVT_VARIANT PropertyValue)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180010840`
- `0x180023548`
- `0x180026450`
- `0x180027a28`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026546`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026546`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall EvtSetChannelConfigProperty(
        EVT_HANDLE ChannelConfig,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId,
        DWORD Flags,
        PEVT_VARIANT PropertyValue)
{
  __int64 v8; // rcx
  BOOL v9; // edi
  DWORD ReferencedObjectAs; // esi
  struct _EVT_VARIANT *v11; // r8
  ChannelConfigObject *v12; // rbx
  ChannelConfigObject *v14; // [rsp+20h] [rbp-58h] BYREF
  EvtException *v15; // [rsp+28h] [rbp-50h] BYREF
  __int128 pExceptionObject; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+40h] [rbp-38h]
  int v18; // [rsp+48h] [rbp-30h]
  int v19; // [rsp+4Ch] [rbp-2Ch]
  int v20; // [rsp+50h] [rbp-28h]

  LastErrInfo::Reset((LastErrInfo *)ChannelConfig);
  try
  {
    v9 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v17 = 0;
      v18 = 87;
      v19 = -1;
      v20 = 1517;
      throw (EvtException *)&pExceptionObject;
    }
    if ( PropertyValue )
    {
      v14 = 0;
      ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(v8, ChannelConfig, &v14);
      if ( ReferencedObjectAs )
      {
        v12 = v14;
      }
      else
      {
        v11 = PropertyValue;
        v12 = v14;
        ReferencedObjectAs = ChannelConfigObject::SetProperty(v14, PropertyId, v11);
      }
      if ( v12 )
        wmi::RefBase::Release(v12);
    }
    else
    {
      ReferencedObjectAs = 87;
    }
  }
  catch ( EvtException *v15 )
  {
    v9 = 0;
    ReferencedObjectAs = *((_DWORD *)v15 + 6);
  }
  SetLastError(ReferencedObjectAs);
  LOBYTE(v9) = ReferencedObjectAs == 0;
  return v9;
}

```

## disassembly

```asm
0x180026450  mov     [rsp+arg_0], rbx
0x180026455  mov     [rsp+arg_8], rsi
0x18002645a  push    rdi
0x18002645b  push    r14
0x18002645d  push    r15
0x18002645f  sub     rsp, 60h
0x180026463  mov     rbx, r9
0x180026466  mov     esi, r8d
0x180026469  mov     r15d, edx
0x18002646c  mov     r14, rcx
0x18002646f  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180026474  xor     edi, edi
0x180026476  test    esi, esi
0x180026478  jz      short loc_1800264EC
0x18002647a  lea     rax, WPP_GLOBAL_Control
0x180026481  mov     rcx, cs:WPP_GLOBAL_Control
0x180026488  cmp     rcx, rax
0x18002648b  jz      short loc_1800264B4
0x18002648d  test    byte ptr [rcx+1Ch], 1
0x180026491  jz      short loc_1800264B4
0x180026493  cmp     byte ptr [rcx+19h], 2
0x180026497  jb      short loc_1800264B4
0x180026499  lea     edx, [rdi+2Fh]
0x18002649c  lea     esi, [rdi+57h]
0x18002649f  mov     r9d, esi
0x1800264a2  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800264a9  mov     rcx, [rcx+10h]
0x1800264ad  call    WPP_SF_D
0x1800264b2  jmp     short loc_1800264B9
0x1800264b4  mov     esi, 57h ; 'W'
0x1800264b9  xorps   xmm0, xmm0
0x1800264bc  movdqu  [rsp+78h+pExceptionObject], xmm0
0x1800264c2  mov     [rsp+78h+var_38], rdi
0x1800264c7  mov     [rsp+78h+var_30], esi
0x1800264cb  mov     [rsp+78h+var_2C], 0FFFFFFFFh
0x1800264d3  mov     [rsp+78h+var_28], 5EDh
0x1800264db  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800264e2  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800264e7  call    _CxxThrowException_0
0x1800264ec  test    rbx, rbx
0x1800264ef  jz      short loc_180026534
0x1800264f1  mov     [rsp+78h+var_58], rdi
0x1800264f6  lea     r8, [rsp+78h+var_58]
0x1800264fb  mov     rdx, r14
0x1800264fe  call    ??$GetReferencedObjectAsType@VChannelConfigObject@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VChannelConfigObject@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(void *,wmi::AutoRef<ChannelConfigObject> &)
0x180026503  mov     esi, eax
0x180026505  test    eax, eax
0x180026507  jnz     short loc_180026520
0x180026509  mov     r8, rbx; struct _EVT_VARIANT *
0x18002650c  mov     edx, r15d; unsigned int
0x18002650f  mov     rbx, [rsp+78h+var_58]
0x180026514  mov     rcx, rbx; this
0x180026517  call    ?SetProperty@ChannelConfigObject@@QEAAKKPEAU_EVT_VARIANT@@@Z; ChannelConfigObject::SetProperty(ulong,_EVT_VARIANT *)
0x18002651c  mov     esi, eax
0x18002651e  jmp     short loc_180026525
0x180026520  mov     rbx, [rsp+78h+var_58]
0x180026525  test    rbx, rbx
0x180026528  jz      short loc_180026539
0x18002652a  mov     rcx, rbx; this
0x18002652d  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x180026532  jmp     short loc_180026539
0x180026534  mov     esi, 57h ; 'W'
0x180026539  jmp     short loc_180026544
0x18002653b  xor     edi, edi
0x18002653d  mov     esi, [rsp+78h+arg_10]
0x180026544  mov     ecx, esi; dwErrCode
0x180026546  call    cs:__imp_SetLastError
0x18002654c  test    esi, esi
0x18002654e  setz    dil
0x180026552  mov     eax, edi
0x180026554  lea     r11, [rsp+78h+var_18]
0x180026559  mov     rbx, [r11+20h]
0x18002655d  mov     rsi, [r11+28h]
0x180026561  mov     rsp, r11
0x180026564  pop     r15
0x180026566  pop     r14
0x180026568  pop     rdi
0x180026569  retn
```
