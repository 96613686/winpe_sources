# CDsmDeviceTask::_RemovePairedDevnodes(tagPROPVARIANT const &,bool *)

- ea: `0x180036680`
- end: `0x1800367ad`
- name: `?_RemovePairedDevnodes@CDsmDeviceTask@@AEAAJAEBUtagPROPVARIANT@@PEA_N@Z`
- size: `301`
- prototype: `__int64 __fastcall(CDsmDeviceTask *__hidden this, const struct tagPROPVARIANT *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800191b0`

## callees

- `0x1800080f0`
- `0x180022070`
- `0x1800363d8`
- `0x180036680`
- `0x1800367b4`
- `0x180036b6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003672e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003675d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003672e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003675d`

## pseudocode

```c
__int64 __fastcall CDsmDeviceTask::_RemovePairedDevnodes(
        CDsmDeviceTask *this,
        const struct tagPROPVARIANT *a2,
        bool *a3)
{
  int v3; // ebx
  __int64 v5; // rdi
  int v7; // r12d
  const unsigned __int16 *v8; // rsi
  CDsmDeviceTask *v9; // rcx
  int v10; // r9d
  bool v11; // bp
  int v12; // edx
  CDsmDeviceTask *v13; // rcx
  int v14; // eax
  __int64 v16; // [rsp+28h] [rbp-30h]
  __int64 v17; // [rsp+30h] [rbp-28h]
  bool v18; // [rsp+68h] [rbp+10h] BYREF
  LPVOID pv; // [rsp+70h] [rbp+18h] BYREF

  v3 = 0;
  *a3 = 0;
  v5 = 0;
  v7 = (int)this;
  while ( (unsigned int)v5 < a2->lVal )
  {
    v8 = *(const unsigned __int16 **)&a2->bstrblobVal.pData[8 * v5];
    pv = 0;
    if ( (int)GetDeviceObjectStringProperty(3, v8, &DEVPKEY_Aep_AepId, 0, &pv, v16, v17) >= 0 )
    {
      v11 = 0;
      v18 = 0;
      v3 = CDsmDeviceTask::_RemovePairedDevnode(v9, v8, (const unsigned __int16 *)pv, v10);
      if ( v3 == -2140930031 )
      {
        v14 = CDsmDeviceTask::_RemovePnPDevnode(v13, v8, &v18);
        v11 = v18;
        v3 = v14;
      }
      if ( v3 < 0 )
      {
        if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 2) != 0 )
          McTemplateU0zjd_EventWriteTransfer((_DWORD)v13, v12, (_DWORD)v8, v7, v3);
        if ( pv )
          CoTaskMemFree(pv);
        break;
      }
      if ( v11 )
        *a3 = 1;
    }
    if ( pv )
      CoTaskMemFree(pv);
    v5 = (unsigned int)(v5 + 1);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids,
      (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180036680  mov     [rsp+arg_0], rbx
0x180036685  mov     [rsp+arg_18], rbp
0x18003668a  push    rsi
0x18003668b  push    rdi
0x18003668c  push    r12
0x18003668e  push    r14
0x180036690  push    r15
0x180036692  sub     rsp, 30h
0x180036696  xor     ebx, ebx
0x180036698  mov     r14, r8
0x18003669b  mov     [r8], bl
0x18003669e  xor     edi, edi
0x1800366a0  mov     r15, rdx
0x1800366a3  mov     r12, rcx
0x1800366a6  cmp     edi, [r15+8]
0x1800366aa  jnb     loc_180036763
0x1800366b0  mov     rax, [r15+10h]
0x1800366b4  lea     r8, DEVPKEY_Aep_AepId
0x1800366bb  xor     r9d, r9d
0x1800366be  mov     rsi, [rax+rdi*8]
0x1800366c2  lea     rax, [rsp+58h+pv]
0x1800366c7  mov     rdx, rsi
0x1800366ca  mov     [rsp+58h+var_38], rax
0x1800366cf  lea     ecx, [r9+3]
0x1800366d3  mov     [rsp+58h+pv], 0
0x1800366dc  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x1800366e1  test    eax, eax
0x1800366e3  js      short loc_180036724
0x1800366e5  mov     r8, [rsp+58h+pv]; unsigned __int16 *
0x1800366ea  xor     bpl, bpl
0x1800366ed  mov     rdx, rsi; unsigned __int16 *
0x1800366f0  mov     [rsp+58h+arg_8], bpl
0x1800366f5  call    ?_RemovePairedDevnode@CDsmDeviceTask@@AEAAJPEBG0@Z; CDsmDeviceTask::_RemovePairedDevnode(ushort const *,ushort const *)
0x1800366fa  mov     ebx, eax
0x1800366fc  cmp     eax, 80640011h
0x180036701  jnz     short loc_180036717
0x180036703  lea     r8, [rsp+58h+arg_8]; bool *
0x180036708  mov     rdx, rsi; unsigned __int16 *
0x18003670b  call    ?_RemovePnPDevnode@CDsmDeviceTask@@AEAAJPEBGPEA_N@Z; CDsmDeviceTask::_RemovePnPDevnode(ushort const *,bool *)
0x180036710  mov     bpl, [rsp+58h+arg_8]
0x180036715  mov     ebx, eax
0x180036717  test    ebx, ebx
0x180036719  js      short loc_18003673B
0x18003671b  test    bpl, bpl
0x18003671e  jz      short loc_180036724
0x180036720  mov     byte ptr [r14], 1
0x180036724  mov     rcx, [rsp+58h+pv]; pv
0x180036729  test    rcx, rcx
0x18003672c  jz      short loc_180036734
0x18003672e  call    cs:__imp_CoTaskMemFree
0x180036734  inc     edi
0x180036736  jmp     loc_1800366A6
0x18003673b  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 2
0x180036742  jz      short loc_180036753
0x180036744  mov     r9, r12
0x180036747  mov     dword ptr [rsp+58h+var_38], ebx
0x18003674b  mov     r8, rsi
0x18003674e  call    McTemplateU0zjd_EventWriteTransfer
0x180036753  mov     rcx, [rsp+58h+pv]; pv
0x180036758  test    rcx, rcx
0x18003675b  jz      short loc_180036763
0x18003675d  call    cs:__imp_CoTaskMemFree
0x180036763  mov     rcx, cs:WPP_GLOBAL_Control
0x18003676a  lea     rax, WPP_GLOBAL_Control
0x180036771  cmp     rcx, rax
0x180036774  jz      short loc_180036794
0x180036776  test    byte ptr [rcx+1Ch], 1
0x18003677a  jz      short loc_180036794
0x18003677c  mov     rcx, [rcx+10h]
0x180036780  lea     r8, WPP_33771ca157e2352e8c67aa8b8aaebcd9_Traceguids
0x180036787  mov     edx, 11h
0x18003678c  mov     r9d, ebx
0x18003678f  call    WPP_SF_d
0x180036794  mov     rbp, [rsp+58h+arg_18]
0x180036799  mov     eax, ebx
0x18003679b  mov     rbx, [rsp+58h+arg_0]
0x1800367a0  add     rsp, 30h
0x1800367a4  pop     r15
0x1800367a6  pop     r14
0x1800367a8  pop     r12
0x1800367aa  pop     rdi
0x1800367ab  pop     rsi
0x1800367ac  retn
```
