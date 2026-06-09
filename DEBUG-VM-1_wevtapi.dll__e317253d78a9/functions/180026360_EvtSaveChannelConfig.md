# EvtSaveChannelConfig

- ea: `0x180026360`
- end: `0x180026448`
- name: `EvtSaveChannelConfig`
- size: `232`
- prototype: `BOOL __stdcall(EVT_HANDLE ChannelConfig, DWORD Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x180006870`
- `0x180006aec`
- `0x180010840`
- `0x180023548`
- `0x180026360`
- `0x18002786c`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002642a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002642a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __stdcall EvtSaveChannelConfig(EVT_HANDLE ChannelConfig, DWORD Flags)
{
  __int64 v4; // rcx
  BOOL v5; // edi
  DWORD ReferencedObjectAs; // esi
  ChannelConfigObject *v7; // rbx
  EvtException *v9; // [rsp+20h] [rbp-38h] BYREF
  __int128 pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  int v12; // [rsp+40h] [rbp-18h]
  int v13; // [rsp+44h] [rbp-14h]
  int v14; // [rsp+48h] [rbp-10h]
  ChannelConfigObject *v15; // [rsp+70h] [rbp+18h] BYREF

  LastErrInfo::Reset((LastErrInfo *)ChannelConfig);
  try
  {
    v5 = 0;
    if ( Flags )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids, 87);
      }
      pExceptionObject = 0;
      v11 = 0;
      v12 = 87;
      v13 = -1;
      v14 = 1478;
      throw (EvtException *)&pExceptionObject;
    }
    v15 = 0;
    ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(v4, ChannelConfig, &v15);
    v7 = v15;
    if ( !ReferencedObjectAs )
      ChannelConfigObject::Save(v15);
    if ( v7 )
      wmi::RefBase::Release(v7);
  }
  catch ( EvtException *v9 )
  {
    v5 = 0;
    ReferencedObjectAs = *((_DWORD *)v9 + 6);
  }
  SetLastError(ReferencedObjectAs);
  LOBYTE(v5) = ReferencedObjectAs == 0;
  return v5;
}

```

## disassembly

```asm
0x180026360  mov     [rsp+arg_0], rbx
0x180026365  mov     [rsp+arg_18], rsi
0x18002636a  push    rdi
0x18002636b  sub     rsp, 50h
0x18002636f  mov     ebx, edx
0x180026371  mov     rsi, rcx
0x180026374  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x180026379  xor     edi, edi
0x18002637b  test    ebx, ebx
0x18002637d  jz      short loc_1800263EC
0x18002637f  lea     rax, WPP_GLOBAL_Control
0x180026386  mov     rcx, cs:WPP_GLOBAL_Control
0x18002638d  cmp     rcx, rax
0x180026390  jz      short loc_1800263B5
0x180026392  test    byte ptr [rcx+1Ch], 1
0x180026396  jz      short loc_1800263B5
0x180026398  cmp     byte ptr [rcx+19h], 2
0x18002639c  jb      short loc_1800263B5
0x18002639e  lea     edx, [rdi+2Eh]
0x1800263a1  lea     r9d, [rdi+57h]
0x1800263a5  lea     r8, WPP_6c6c805d13ef39f517b43cdeae326efa_Traceguids
0x1800263ac  mov     rcx, [rcx+10h]
0x1800263b0  call    WPP_SF_D
0x1800263b5  xorps   xmm0, xmm0
0x1800263b8  movdqu  [rsp+58h+pExceptionObject], xmm0
0x1800263be  mov     [rsp+58h+var_20], rdi
0x1800263c3  mov     [rsp+58h+var_18], 57h ; 'W'
0x1800263cb  mov     [rsp+58h+var_14], 0FFFFFFFFh
0x1800263d3  mov     [rsp+58h+var_10], 5C6h
0x1800263db  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800263e2  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800263e7  call    _CxxThrowException_0
0x1800263ec  mov     [rsp+58h+arg_10], rdi
0x1800263f1  lea     r8, [rsp+58h+arg_10]
0x1800263f6  mov     rdx, rsi
0x1800263f9  call    ??$GetReferencedObjectAsType@VChannelConfigObject@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VChannelConfigObject@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<ChannelConfigObject,void>(void *,wmi::AutoRef<ChannelConfigObject> &)
0x1800263fe  mov     esi, eax
0x180026400  mov     rbx, [rsp+58h+arg_10]
0x180026405  test    eax, eax
0x180026407  jnz     short loc_180026412
0x180026409  mov     rcx, rbx; this
0x18002640c  call    ?Save@ChannelConfigObject@@QEAAXXZ; ChannelConfigObject::Save(void)
0x180026411  nop
0x180026412  test    rbx, rbx
0x180026415  jz      short loc_180026420
0x180026417  mov     rcx, rbx; this
0x18002641a  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18002641f  nop
0x180026420  jmp     short loc_180026428
0x180026422  xor     edi, edi
0x180026424  mov     esi, [rsp+58h+arg_8]
0x180026428  mov     ecx, esi; dwErrCode
0x18002642a  call    cs:__imp_SetLastError
0x180026430  test    esi, esi
0x180026432  setz    dil
0x180026436  mov     eax, edi
0x180026438  mov     rbx, [rsp+58h+arg_0]
0x18002643d  mov     rsi, [rsp+58h+arg_18]
0x180026442  add     rsp, 50h
0x180026446  pop     rdi
0x180026447  retn
```
