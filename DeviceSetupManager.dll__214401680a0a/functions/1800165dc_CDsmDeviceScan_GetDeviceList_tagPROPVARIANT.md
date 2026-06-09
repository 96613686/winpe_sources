# CDsmDeviceScan::_GetDeviceList(tagPROPVARIANT *)

- ea: `0x1800165dc`
- end: `0x1800167c8`
- name: `?_GetDeviceList@CDsmDeviceScan@@AEAAJPEAUtagPROPVARIANT@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(CDsmDeviceScan *this, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002ed44`

## callees

- `0x18000af34`
- `0x1800165dc`
- `0x180016c18`
- `0x18001af70`
- `0x18001ba48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016786`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016786`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001662f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001662f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001672f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x18001672f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001661e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016793`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001661e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016793`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016677`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001676f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016745`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001676f`

## pseudocode

```c
__int64 __fastcall CDsmDeviceScan::_GetDeviceList(CDsmDeviceScan *this, PROPVARIANT *a2)
{
  CDsmDeviceScan *v3; // r15
  PROPVARIANT *v4; // r14
  HRESULT v5; // ebx
  unsigned int v6; // edi
  void *v7; // rax
  PROPVARIANT *v8; // r12
  unsigned int i; // esi
  __int64 *v10; // rdx
  IID v11; // xmm6
  __int64 v12; // rax
  LPOLESTR v13; // rdx
  __int64 v15; // r9
  _QWORD *v16; // rcx
  __int64 *v17; // rdx
  __int64 v18; // [rsp+0h] [rbp-C8h] BYREF
  LPOLESTR lpsz; // [rsp+28h] [rbp-A0h] BYREF
  unsigned int v20; // [rsp+30h] [rbp-98h]
  unsigned int v21; // [rsp+34h] [rbp-94h]
  PROPVARIANT *pvar; // [rsp+38h] [rbp-90h]
  CDsmDeviceScan *v23; // [rsp+40h] [rbp-88h]
  PROPVARIANT *v24; // [rsp+50h] [rbp-78h]
  PSRWLOCK SRWLock; // [rsp+58h] [rbp-70h]
  ATL::CAtlException *v26; // [rsp+68h] [rbp-60h] BYREF
  IID rclsid; // [rsp+70h] [rbp-58h] BYREF

  v3 = this;
  v23 = this;
  v4 = a2;
  pvar = a2;
  PropVariantClear(a2);
  v5 = 0;
  SRWLock = (PSRWLOCK)((char *)v3 + 32);
  AcquireSRWLockExclusive((PSRWLOCK)v3 + 4);
  v20 = *((_DWORD *)v3 + 14);
  v6 = v20;
  if ( v20 )
  {
    *(_WORD *)a2 = 4127;
    *((_DWORD *)v4 + 2) = v6;
    v7 = CoTaskMemAlloc(8LL * v6);
    v8 = v4 + 2;
    v4[2] = v7;
    if ( v7 )
    {
      v24 = v4 + 2;
      v5 = 0;
      memset_0(v7, 0, 8LL * v6);
      i = 0;
      while ( 2 )
      {
        v21 = i;
        if ( i >= v6 )
          goto LABEL_17;
        rclsid = 0;
        v10 = (__int64 *)*((_QWORD *)v3 + 5);
        if ( v10 )
          break;
        if ( __eh34_try(-1, 2) )
        {
          __eh34_scope_strut(2);
          ATL::AtlThrowImpl(-2147467259);
        }
        if ( __eh34_catch(2) )
        {
          if ( __eh34_catch_type(2, &ATL::CAtlException `RTTI Type Descriptor', &v26) )
          {
            v17 = &v18;
            v15 = *(unsigned int *)v17[13];
            *((_DWORD *)v17 + 8) = v15;
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 )
              WPP_SF_d(v16[2], 39, &WPP_43d4499022663c6448c6fdf63854fbee_Traceguids, v15);
            v6 = v20;
            i = v21;
            v3 = v23;
            v4 = pvar;
            v8 = v24;
            __eh34_try_continuation(2, &ATL::CAtlException `RTTI Type Descriptor', &loc_1800166FD);
LABEL_10:
            lpsz = 0;
            v5 = StringFromIID(&rclsid, &lpsz);
            if ( v5 < 0 )
            {
              if ( lpsz )
                CoTaskMemFree(lpsz);
              goto LABEL_17;
            }
            v13 = lpsz;
            lpsz = 0;
            *((_QWORD *)*v8 + i) = v13;
            if ( lpsz )
              CoTaskMemFree(lpsz);
            ++i;
            continue;
          }
        }
        break;
      }
      v11 = (IID)*((_OWORD *)v10 + 1);
      v12 = *v10;
      *((_QWORD *)v3 + 5) = *v10;
      if ( v12 )
        *(_QWORD *)(v12 + 8) = 0;
      else
        *((_QWORD *)v3 + 6) = 0;
      ATL::CAtlList<_GUID,ATL::CElementTraits<_GUID>>::FreeNode();
      rclsid = v11;
      goto LABEL_10;
    }
    v5 = -2147024882;
  }
LABEL_17:
  ReleaseSRWLockExclusive(SRWLock);
  if ( v5 < 0 )
    PropVariantClear(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800165dc  mov     rax, rsp
0x1800165df  mov     [rax+18h], rbx
0x1800165e3  push    rsi
0x1800165e4  push    rdi
0x1800165e5  push    r12
0x1800165e7  push    r14
0x1800165e9  push    r15
0x1800165eb  sub     rsp, 0A0h
0x1800165f2  movaps  xmmword ptr [rax-38h], xmm6
0x1800165f6  mov     rax, cs:__security_cookie
0x1800165fd  xor     rax, rsp
0x180016600  mov     [rsp+0C8h+var_48], rax
0x180016608  mov     rsi, rdx
0x18001660b  mov     r15, rcx
0x18001660e  mov     [rsp+0C8h+var_88], rcx
0x180016613  mov     r14, rdx
0x180016616  mov     [rsp+0C8h+pvar], rdx
0x18001661b  mov     rcx, rdx; pvar
0x18001661e  call    cs:__imp_PropVariantClear
0x180016624  xor     ebx, ebx
0x180016626  lea     rcx, [r15+20h]; SRWLock
0x18001662a  mov     [rsp+0C8h+SRWLock], rcx
0x18001662f  call    cs:__imp_AcquireSRWLockExclusive
0x180016635  nop
0x180016636  mov     edi, [r15+38h]
0x18001663a  mov     [rsp+0C8h+var_98], edi
0x18001663e  jmp     short loc_18001665D
0x180016640  mov     ebx, [rsp+0C8h+var_A8]
0x180016644  mov     r14, [rsp+0C8h+pvar]
0x180016649  test    ebx, ebx
0x18001664b  js      loc_180016781
0x180016651  mov     edi, [rsp+0C8h+var_98]
0x180016655  mov     r15, [rsp+0C8h+var_88]
0x18001665a  mov     rsi, r14
0x18001665d  test    edi, edi
0x18001665f  jz      loc_180016781
0x180016665  mov     word ptr [rsi], 101Fh
0x18001666a  mov     [r14+8], edi
0x18001666e  mov     esi, edi
0x180016670  shl     rsi, 3
0x180016674  mov     rcx, rsi; cb
0x180016677  call    cs:__imp_CoTaskMemAlloc
0x18001667d  lea     r12, [r14+10h]
0x180016681  mov     [r12], rax
0x180016685  test    rax, rax
0x180016688  jz      loc_18001677C
0x18001668e  mov     [rsp+0C8h+var_78], r12
0x180016693  xor     ebx, ebx
0x180016695  mov     r8, rsi; Size
0x180016698  xor     edx, edx; Val
0x18001669a  mov     rcx, rax; void *
0x18001669d  call    memset_0
0x1800166a2  xor     esi, esi
0x1800166a4  mov     [rsp+0C8h+var_94], esi
0x1800166a8  cmp     esi, edi
0x1800166aa  jnb     loc_180016781
0x1800166b0  xorps   xmm0, xmm0
0x1800166b3  movups  xmmword ptr [rsp+0C8h+rclsid.Data1], xmm0
0x1800166b8  lea     rcx, [r15+28h]
0x1800166bc  mov     rdx, [rcx]
0x1800166bf  test    rdx, rdx
0x1800166c2  jz      short loc_1800166F2
0x1800166c4  movups  xmm6, xmmword ptr [rdx+10h]
0x1800166c8  mov     rax, [rdx]
0x1800166cb  mov     [rcx], rax
0x1800166ce  test    rax, rax
0x1800166d1  jz      short loc_1800166DD
0x1800166d3  mov     qword ptr [rax+8], 0
0x1800166db  jmp     short loc_1800166E5
0x1800166dd  mov     qword ptr [rcx+8], 0
0x1800166e5  call    ?FreeNode@?$CAtlList@U_GUID@@V?$CElementTraits@U_GUID@@@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<_GUID,ATL::CElementTraits<_GUID>>::FreeNode(ATL::CAtlList<_GUID,ATL::CElementTraits<_GUID>>::CNode *)
0x1800166ea  movdqa  xmmword ptr [rsp+0C8h+rclsid.Data1], xmm6
0x1800166f0  jmp     short loc_180016718
0x1800166f2  mov     ecx, 80004005h; int
0x1800166f7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800166fd  mov     edi, [rsp+0C8h+var_98]
0x180016701  mov     ebx, [rsp+0C8h+var_A8]
0x180016705  mov     esi, [rsp+0C8h+var_94]
0x180016709  mov     r15, [rsp+0C8h+var_88]
0x18001670e  mov     r14, [rsp+0C8h+pvar]
0x180016713  mov     r12, [rsp+0C8h+var_78]
0x180016718  test    ebx, ebx
0x18001671a  js      short loc_180016781
0x18001671c  mov     [rsp+0C8h+lpsz], 0
0x180016725  lea     rdx, [rsp+0C8h+lpsz]; lplpsz
0x18001672a  lea     rcx, [rsp+0C8h+rclsid]; rclsid
0x18001672f  call    cs:__imp_StringFromIID
0x180016735  mov     ebx, eax
0x180016737  test    eax, eax
0x180016739  jns     short loc_18001674D
0x18001673b  mov     rcx, [rsp+0C8h+lpsz]; pv
0x180016740  test    rcx, rcx
0x180016743  jz      short loc_180016781
0x180016745  call    cs:__imp_CoTaskMemFree
0x18001674b  jmp     short loc_180016781
0x18001674d  mov     rdx, [rsp+0C8h+lpsz]
0x180016752  mov     [rsp+0C8h+lpsz], 0
0x18001675b  mov     ecx, esi
0x18001675d  mov     rax, [r12]
0x180016761  mov     [rax+rcx*8], rdx
0x180016765  mov     rcx, [rsp+0C8h+lpsz]; pv
0x18001676a  test    rcx, rcx
0x18001676d  jz      short loc_180016775
0x18001676f  call    cs:__imp_CoTaskMemFree
0x180016775  inc     esi
0x180016777  jmp     loc_1800166A4
0x18001677c  mov     ebx, 8007000Eh
0x180016781  mov     rcx, [rsp+0C8h+SRWLock]; SRWLock
0x180016786  call    cs:__imp_ReleaseSRWLockExclusive
0x18001678c  test    ebx, ebx
0x18001678e  jns     short loc_180016799
0x180016790  mov     rcx, r14; pvar
0x180016793  call    cs:__imp_PropVariantClear
0x180016799  mov     eax, ebx
0x18001679b  mov     rcx, [rsp+0C8h+var_48]
0x1800167a3  xor     rcx, rsp; StackCookie
0x1800167a6  call    __security_check_cookie
0x1800167ab  lea     r11, [rsp+0C8h+var_28]
0x1800167b3  mov     rbx, [r11+40h]
0x1800167b7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800167bc  mov     rsp, r11
0x1800167bf  pop     r15
0x1800167c1  pop     r14
0x1800167c3  pop     r12
0x1800167c5  pop     rdi
0x1800167c6  pop     rsi
0x1800167c7  retn
```
