# CWfHelperClass::CreateAndSetAttributes(_hypothesis_builder *,ushort const *,ushort,ushort,ushort)

- ea: `0x1800033a0`
- end: `0x1800037c8`
- name: `?CreateAndSetAttributes@CWfHelperClass@@AEAAJPEAV_hypothesis_builder@@PEBGGGG@Z`
- size: `1064`
- prototype: `int __fastcall(CWfHelperClass *this, struct _hypothesis_builder *, const unsigned __int16 *, __int16, unsigned __int16, u_short)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002c10`

## callees

- `0x1800031e0`
- `0x1800033a0`
- `0x180003b60`
- `0x180005c60`
- `0x180005ce0`
- `0x1800079b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800034fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000360a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000370c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800034fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000360a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000370c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800033ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800033fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000341c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000363a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800033ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800033fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000341c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003426`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800035c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000363a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800036d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003789`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003792`
- `WS2_32!__imp_htons` at `0x1800034ae`
- `WS2_32!__imp_htons` at `0x1800034ae`

## string_xrefs

- `0x1800036d8`: `protocol`
- `0x180003726`: `protocol`

## pseudocode

```c
int __fastcall CWfHelperClass::CreateAndSetAttributes(
        CWfHelperClass *this,
        struct _hypothesis_builder *a2,
        const unsigned __int16 *a3,
        __int16 a4,
        unsigned __int16 a5,
        u_short a6)
{
  void *v6; // rcx
  void *v10; // rcx
  __int64 v11; // rcx
  void *v12; // rcx
  int result; // eax
  unsigned int v14; // edx
  LPWSTR pwszName; // rbx
  const wchar_t *v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rdi
  WCHAR *v19; // rax
  ATTRIBUTE_TYPE type; // eax
  int v21; // r15d
  int v22; // edi
  void *PWStr; // rcx
  __int64 v24; // rcx
  const wchar_t *v25; // rax
  __int64 v26; // rbx
  WCHAR *v27; // rax
  int v28; // edi
  ATTRIBUTE_TYPE v29; // ebx
  void *lpValue; // rcx
  LPWSTR v31; // rbx
  const wchar_t *v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rsi
  WCHAR *v35; // rax
  bool v36; // cf
  ATTRIBUTE_TYPE v37; // ecx
  void *v38; // rcx
  tagHELPER_ATTRIBUTE v39; // [rsp+20h] [rbp-E0h] BYREF
  union tagHELPER_ATTRIBUTE::$E73CE4DD3AF9771F1CA4F78E7E603792 v40; // [rsp+B0h] [rbp-50h] BYREF

  v6 = *(void **)a2;
  memset(&v40.Int64 + 1, 0, 120);
  CoTaskMemFree(v6);
  v10 = (void *)*((_QWORD *)a2 + 1);
  *(_QWORD *)a2 = 0;
  CoTaskMemFree(v10);
  *((_QWORD *)a2 + 1) = 0;
  _attributes_array_t::FreeElements((struct _hypothesis_builder *)((char *)a2 + 16));
  v11 = *((_QWORD *)a2 + 4);
  if ( v11 )
    CoTaskMemFree(*(LPVOID *)(v11 + 24));
  CoTaskMemFree(*((LPVOID *)a2 + 4));
  v12 = *(void **)a2;
  *((_QWORD *)a2 + 4) = 0;
  CoTaskMemFree(v12);
  *(_QWORD *)a2 = 0;
  result = StringCchCopyWithAlloc((unsigned __int16 **)a2, 0xFFFFu, L"FilteringPlatform");
  if ( result >= 0 )
  {
    result = _hypothesis_builder::SetCount(a2, v14);
    if ( result >= 0 )
    {
      v40.LifeTime.startTime.dwHighDateTime = 0;
      if ( a4 == 23 )
      {
        v40.Short = 23;
        memset(&v40.Int64 + 1, 0, 20);
      }
      else
      {
        v40.Short = 2;
        v40.OctetString.lpValue = 0;
      }
      *((_WORD *)&v40.Char + 1) = htons(a6);
      CoTaskMemFree(0);
      pwszName = 0;
      v16 = L"localaddr";
      v39.pwszName = 0;
      v17 = 65534;
      do
      {
        if ( !*v16 )
          break;
        ++v16;
        --v17;
      }
      while ( v17 );
      v18 = 65534 - v17;
      if ( v17 )
      {
        v19 = (WCHAR *)CoTaskMemAlloc(2 * v18 + 2);
        v39.pwszName = v19;
        pwszName = v19;
        if ( v19 )
          StringCchCopyW(v19, v18 + 1, L"localaddr");
      }
      type = AT_SOCKADDR;
      v21 = -2147024809;
      v39.type = AT_SOCKADDR;
      v39.16 = v40;
      if ( pwszName )
      {
        _attribute_t::Copy(*((struct tagHELPER_ATTRIBUTE **)a2 + 3), &v39);
        type = v39.type;
        v22 = 0;
        pwszName = v39.pwszName;
      }
      else
      {
        v22 = -2147024809;
      }
      if ( type == AT_STRING )
      {
        PWStr = v39.PWStr;
      }
      else
      {
        if ( type != AT_OCTET_STRING )
          goto LABEL_22;
        PWStr = v39.OctetString.lpValue;
      }
      CoTaskMemFree(PWStr);
LABEL_22:
      CoTaskMemFree(pwszName);
      if ( v22 < 0 )
        return v22;
      CoTaskMemFree(0);
      v24 = 65534;
      v39.pwszName = 0;
      v25 = L"appid";
      do
      {
        if ( !*v25 )
          break;
        ++v25;
        --v24;
      }
      while ( v24 );
      v26 = 65534 - v24;
      if ( v24 )
      {
        v27 = (WCHAR *)CoTaskMemAlloc(2 * v26 + 2);
        v39.pwszName = v27;
        if ( v27 )
          StringCchCopyW(v27, v26 + 1, L"appid");
      }
      v28 = 10;
      v29 = AT_STRING;
      v39.type = AT_STRING;
      CoTaskMemFree(0);
      v39.Int64 = 0;
      if ( a3 )
      {
        if ( StringCchCopyWithAlloc(&v39.PWStr, 0xFFFFu, a3) < 0 )
        {
          v29 = AT_INVALID;
          v28 = 0;
        }
        v39.type = v29;
      }
      if ( *((_DWORD *)a2 + 4) && v28 && v39.pwszName )
      {
        _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)(*((_QWORD *)a2 + 3) + 144LL), &v39);
        v29 = v39.type;
        v22 = 0;
      }
      else
      {
        v22 = -2147024809;
      }
      if ( v29 == AT_STRING )
      {
        lpValue = v39.PWStr;
      }
      else
      {
        if ( v29 != AT_OCTET_STRING )
          goto LABEL_43;
        lpValue = v39.OctetString.lpValue;
      }
      CoTaskMemFree(lpValue);
LABEL_43:
      CoTaskMemFree(v39.pwszName);
      if ( v22 >= 0 )
      {
        CoTaskMemFree(0);
        v31 = 0;
        v32 = L"protocol";
        v39.pwszName = 0;
        v33 = 65534;
        do
        {
          if ( !*v32 )
            break;
          ++v32;
          --v33;
        }
        while ( v33 );
        v34 = 65534 - v33;
        if ( v33 )
        {
          v35 = (WCHAR *)CoTaskMemAlloc(2 * v34 + 2);
          v39.pwszName = v35;
          v31 = v35;
          if ( v35 )
            StringCchCopyW(v35, v34 + 1, L"protocol");
        }
        v36 = *((_DWORD *)a2 + 4) < 2u;
        v37 = AT_UINT32;
        v39.type = AT_UINT32;
        v39.Boolean = a5;
        if ( !v36 )
        {
          if ( v31 )
          {
            _attribute_t::Copy((struct tagHELPER_ATTRIBUTE *)(*((_QWORD *)a2 + 3) + 288LL), &v39);
            v37 = v39.type;
            v21 = 0;
            v31 = v39.pwszName;
          }
        }
        if ( v37 == AT_STRING )
        {
          v38 = v39.PWStr;
        }
        else
        {
          if ( v37 != AT_OCTET_STRING )
          {
LABEL_58:
            CoTaskMemFree(v31);
            return v21;
          }
          v38 = v39.OctetString.lpValue;
        }
        CoTaskMemFree(v38);
        goto LABEL_58;
      }
      return v22;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800033a0  mov     [rsp-8+arg_10], rbx
0x1800033a5  push    rbp
0x1800033a6  push    r12
0x1800033a8  push    r13
0x1800033aa  push    r14
0x1800033ac  push    r15
0x1800033ae  lea     rbp, [rsp-30h]
0x1800033b3  sub     rsp, 130h
0x1800033ba  mov     rcx, [rdx]; pv
0x1800033bd  xorps   xmm0, xmm0
0x1800033c0  xor     eax, eax
0x1800033c2  movzx   ebx, r9w
0x1800033c6  movups  [rbp+50h+var_A0+8], xmm0
0x1800033ca  mov     [rbp+50h+var_28], rax
0x1800033ce  mov     r12, r8
0x1800033d1  movups  [rbp+50h+var_88], xmm0
0x1800033d5  mov     r14, rdx
0x1800033d8  movups  [rbp+50h+var_78], xmm0
0x1800033dc  movups  [rbp+50h+var_68], xmm0
0x1800033e0  movups  [rbp+50h+var_58], xmm0
0x1800033e4  movups  [rbp+50h+var_48], xmm0
0x1800033e8  movups  [rbp+50h+var_38], xmm0
0x1800033ec  call    cs:__imp_CoTaskMemFree
0x1800033f2  mov     rcx, [r14+8]; pv
0x1800033f6  xor     r15d, r15d
0x1800033f9  mov     [r14], r15
0x1800033fc  call    cs:__imp_CoTaskMemFree
0x180003402  lea     rcx, [r14+10h]; this
0x180003406  mov     [r14+8], r15
0x18000340a  call    ?FreeElements@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeElements(void)
0x18000340f  mov     rcx, [r14+20h]
0x180003413  test    rcx, rcx
0x180003416  jz      short loc_180003422
0x180003418  mov     rcx, [rcx+18h]; pv
0x18000341c  call    cs:__imp_CoTaskMemFree
0x180003422  mov     rcx, [r14+20h]; pv
0x180003426  call    cs:__imp_CoTaskMemFree
0x18000342c  mov     rcx, [r14]; pv
0x18000342f  mov     [r14+20h], r15
0x180003433  call    cs:__imp_CoTaskMemFree
0x180003439  lea     r8, aFilteringplatf; "FilteringPlatform"
0x180003440  mov     [r14], r15
0x180003443  mov     edx, 0FFFFh; unsigned __int64
0x180003448  mov     rcx, r14; unsigned __int16 **
0x18000344b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180003450  test    eax, eax
0x180003452  js      loc_1800037AF
0x180003458  mov     rcx, r14; this
0x18000345b  call    ?SetCount@_hypothesis_builder@@QEAAJK@Z; _hypothesis_builder::SetCount(ulong)
0x180003460  test    eax, eax
0x180003462  js      loc_1800037AF
0x180003468  mov     [rsp+150h+arg_0], rsi
0x180003470  mov     [rsp+150h+arg_8], rdi
0x180003478  mov     dword ptr [rbp+50h+var_A0+4], r15d
0x18000347c  cmp     bx, 17h
0x180003480  jnz     short loc_180003498
0x180003482  mov     eax, 17h
0x180003487  mov     dword ptr [rbp+50h+var_88], r15d
0x18000348b  xorps   xmm0, xmm0
0x18000348e  mov     word ptr [rbp+50h+var_A0], ax
0x180003492  movups  [rbp+50h+var_A0+8], xmm0
0x180003496  jmp     short loc_1800034A7
0x180003498  mov     eax, 2
0x18000349d  mov     word ptr [rbp+50h+var_A0], ax
0x1800034a1  xor     eax, eax
0x1800034a3  mov     qword ptr [rbp+50h+var_A0+8], rax
0x1800034a7  movzx   ecx, [rbp+50h+arg_28]; hostshort
0x1800034ae  call    cs:__imp_htons
0x1800034b4  xor     ecx, ecx; pv
0x1800034b6  mov     word ptr [rbp+50h+var_A0+2], ax
0x1800034ba  call    cs:__imp_CoTaskMemFree
0x1800034c0  mov     rbx, r15
0x1800034c3  lea     rax, aLocaladdr; "localaddr"
0x1800034ca  mov     esi, 0FFFEh
0x1800034cf  mov     [rsp+150h+var_130.pwszName], rbx
0x1800034d4  mov     ecx, esi
0x1800034d6  cmp     [rax], bx
0x1800034d9  jz      short loc_1800034E5
0x1800034db  add     rax, 2
0x1800034df  sub     rcx, 1
0x1800034e3  jnz     short loc_1800034D6
0x1800034e5  mov     rdi, rsi
0x1800034e8  sub     rdi, rcx
0x1800034eb  test    rcx, rcx
0x1800034ee  cmovz   rdi, r15
0x1800034f2  jz      short loc_180003522
0x1800034f4  lea     rcx, ds:2[rdi*2]; cb
0x1800034fc  call    cs:__imp_CoTaskMemAlloc
0x180003502  mov     [rsp+150h+var_130.pwszName], rax
0x180003507  mov     rbx, rax
0x18000350a  test    rax, rax
0x18000350d  jz      short loc_180003522
0x18000350f  lea     rdx, [rdi+1]; unsigned __int64
0x180003513  mov     rcx, rax; unsigned __int16 *
0x180003516  lea     r8, aLocaladdr; "localaddr"
0x18000351d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003522  movaps  xmm0, [rbp+50h+var_A0]
0x180003526  mov     eax, 0Dh
0x18000352b  movaps  xmm1, xmmword ptr [rbp-40h]
0x18000352f  mov     r15d, 80070057h
0x180003535  mov     [rsp+150h+var_130.type], eax
0x180003539  movups  xmmword ptr [rsp+150h+var_130.10h], xmm0
0x18000353e  movaps  xmm0, [rbp+50h+var_88+8]
0x180003542  movups  xmmword ptr [rsp+150h+var_130.10h+10h], xmm1
0x180003547  movaps  xmm1, [rbp+50h+var_78+8]
0x18000354b  movups  xmmword ptr [rsp+150h+var_130.10h+20h], xmm0
0x180003550  movaps  xmm0, [rbp+50h+var_68+8]
0x180003554  movups  xmmword ptr [rsp+150h+var_130.10h+30h], xmm1
0x180003559  movaps  xmm1, [rbp+50h+var_58+8]
0x18000355d  movups  xmmword ptr [rsp+150h+var_130.10h+40h], xmm0
0x180003562  movaps  xmm0, [rbp+50h+var_48+8]
0x180003566  movups  xmmword ptr [rbp+50h+var_130.10h+50h], xmm1
0x18000356a  movaps  xmm1, [rbp+50h+var_38+8]
0x18000356e  movups  xmmword ptr [rbp+50h+var_130.10h+60h], xmm0
0x180003572  movups  xmmword ptr [rbp+50h+var_130.10h+70h], xmm1
0x180003576  test    rbx, rbx
0x180003579  jnz     short loc_180003580
0x18000357b  mov     edi, r15d
0x18000357e  jmp     short loc_180003599
0x180003580  mov     rcx, [r14+18h]; this
0x180003584  lea     rdx, [rsp+150h+var_130]; struct tagHELPER_ATTRIBUTE *
0x180003589  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x18000358e  mov     eax, [rsp+150h+var_130.type]
0x180003592  xor     edi, edi
0x180003594  mov     rbx, [rsp+150h+var_130.pwszName]
0x180003599  cmp     eax, 0Ah
0x18000359c  jnz     short loc_1800035A5
0x18000359e  mov     rcx, qword ptr [rsp+150h+var_130.10h]
0x1800035a3  jmp     short loc_1800035AF
0x1800035a5  cmp     eax, 0Eh
0x1800035a8  jnz     short loc_1800035B5
0x1800035aa  mov     rcx, qword ptr [rsp+150h+var_130.10h+8]; pv
0x1800035af  call    cs:__imp_CoTaskMemFree
0x1800035b5  mov     rcx, rbx; pv
0x1800035b8  call    cs:__imp_CoTaskMemFree
0x1800035be  test    edi, edi
0x1800035c0  js      loc_18000379D
0x1800035c6  xor     ecx, ecx; pv
0x1800035c8  call    cs:__imp_CoTaskMemFree
0x1800035ce  mov     rcx, rsi
0x1800035d1  mov     [rsp+150h+var_130.pwszName], 0
0x1800035da  lea     rax, aAppid; "appid"
0x1800035e1  cmp     word ptr [rax], 0
0x1800035e5  jz      short loc_1800035F1
0x1800035e7  add     rax, 2
0x1800035eb  sub     rcx, 1
0x1800035ef  jnz     short loc_1800035E1
0x1800035f1  xor     eax, eax
0x1800035f3  mov     rbx, rsi
0x1800035f6  sub     rbx, rcx
0x1800035f9  test    rcx, rcx
0x1800035fc  cmovz   rbx, rax
0x180003600  jz      short loc_18000362D
0x180003602  lea     rcx, ds:2[rbx*2]; cb
0x18000360a  call    cs:__imp_CoTaskMemAlloc
0x180003610  mov     [rsp+150h+var_130.pwszName], rax
0x180003615  test    rax, rax
0x180003618  jz      short loc_18000362D
0x18000361a  lea     rdx, [rbx+1]; unsigned __int64
0x18000361e  mov     rcx, rax; unsigned __int16 *
0x180003621  lea     r8, aAppid; "appid"
0x180003628  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000362d  mov     edi, 0Ah
0x180003632  xor     ecx, ecx; pv
0x180003634  mov     ebx, edi
0x180003636  mov     [rsp+150h+var_130.type], ebx
0x18000363a  call    cs:__imp_CoTaskMemFree
0x180003640  mov     qword ptr [rsp+150h+var_130.10h], 0
0x180003649  test    r12, r12
0x18000364c  jz      short loc_18000366C
0x18000364e  mov     r8, r12; unsigned __int16 *
0x180003651  lea     rcx, [rsp+150h+var_130.10h]; unsigned __int16 **
0x180003656  mov     edx, 0FFFFh; unsigned __int64
0x18000365b  call    ?StringCchCopyWithAlloc@@YAJPEAPEAG_KPEBG@Z; StringCchCopyWithAlloc(ushort * *,unsigned __int64,ushort const *)
0x180003660  test    eax, eax
0x180003662  jns     short loc_180003668
0x180003664  xor     ebx, ebx
0x180003666  xor     edi, edi
0x180003668  mov     [rsp+150h+var_130.type], ebx
0x18000366c  cmp     dword ptr [r14+10h], 1
0x180003671  jb      short loc_18000369C
0x180003673  test    edi, edi
0x180003675  jz      short loc_18000369C
0x180003677  cmp     [rsp+150h+var_130.pwszName], 0
0x18000367d  jz      short loc_18000369C
0x18000367f  mov     rcx, [r14+18h]
0x180003683  lea     rdx, [rsp+150h+var_130]; struct tagHELPER_ATTRIBUTE *
0x180003688  add     rcx, 90h; this
0x18000368f  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180003694  mov     ebx, [rsp+150h+var_130.type]
0x180003698  xor     edi, edi
0x18000369a  jmp     short loc_18000369F
0x18000369c  mov     edi, r15d
0x18000369f  cmp     ebx, 0Ah
0x1800036a2  jnz     short loc_1800036AB
0x1800036a4  mov     rcx, qword ptr [rsp+150h+var_130.10h]
0x1800036a9  jmp     short loc_1800036B5
0x1800036ab  cmp     ebx, 0Eh
0x1800036ae  jnz     short loc_1800036BB
0x1800036b0  mov     rcx, qword ptr [rsp+150h+var_130.10h+8]; pv
0x1800036b5  call    cs:__imp_CoTaskMemFree
0x1800036bb  mov     rcx, [rsp+150h+var_130.pwszName]; pv
0x1800036c0  call    cs:__imp_CoTaskMemFree
0x1800036c6  test    edi, edi
0x1800036c8  js      loc_18000379D
0x1800036ce  xor     ecx, ecx; pv
0x1800036d0  call    cs:__imp_CoTaskMemFree
0x1800036d6  xor     ebx, ebx
0x1800036d8  lea     rax, aProtocol; "protocol"
0x1800036df  mov     [rsp+150h+var_130.pwszName], rbx
0x1800036e4  mov     rcx, rsi
0x1800036e7  cmp     [rax], bx
0x1800036ea  jz      short loc_1800036F6
0x1800036ec  add     rax, 2
0x1800036f0  sub     rcx, 1
0x1800036f4  jnz     short loc_1800036E7
0x1800036f6  sub     rsi, rcx
0x1800036f9  xor     eax, eax
0x1800036fb  test    rcx, rcx
0x1800036fe  cmovz   rsi, rax
0x180003702  jz      short loc_180003732
0x180003704  lea     rcx, ds:2[rsi*2]; cb
0x18000370c  call    cs:__imp_CoTaskMemAlloc
0x180003712  mov     [rsp+150h+var_130.pwszName], rax
0x180003717  mov     rbx, rax
0x18000371a  test    rax, rax
0x18000371d  jz      short loc_180003732
0x18000371f  lea     rdx, [rsi+1]; unsigned __int64
0x180003723  mov     rcx, rax; unsigned __int16 *
0x180003726  lea     r8, aProtocol; "protocol"
0x18000372d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180003732  cmp     dword ptr [r14+10h], 2
0x180003737  mov     ecx, 7
0x18000373c  movzx   eax, [rbp+50h+arg_20]
0x180003743  mov     [rsp+150h+var_130.type], ecx
0x180003747  mov     dword ptr [rsp+150h+var_130.10h], eax
0x18000374b  jb      short loc_180003773
0x18000374d  test    rbx, rbx
0x180003750  jz      short loc_180003773
0x180003752  mov     rcx, [r14+18h]
0x180003756  lea     rdx, [rsp+150h+var_130]; struct tagHELPER_ATTRIBUTE *
0x18000375b  add     rcx, 120h; this
0x180003762  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180003767  mov     ecx, [rsp+150h+var_130.type]
0x18000376b  xor     r15d, r15d
0x18000376e  mov     rbx, [rsp+150h+var_130.pwszName]
0x180003773  cmp     ecx, 0Ah
0x180003776  jnz     short loc_18000377F
0x180003778  mov     rcx, qword ptr [rsp+150h+var_130.10h]
0x18000377d  jmp     short loc_180003789
0x18000377f  cmp     ecx, 0Eh
0x180003782  jnz     short loc_18000378F
0x180003784  mov     rcx, qword ptr [rsp+150h+var_130.10h+8]; pv
0x180003789  call    cs:__imp_CoTaskMemFree
0x18000378f  mov     rcx, rbx; pv
0x180003792  call    cs:__imp_CoTaskMemFree
0x180003798  mov     eax, r15d
0x18000379b  jmp     short loc_18000379F
0x18000379d  mov     eax, edi
0x18000379f  mov     rsi, [rsp+150h+arg_0]
0x1800037a7  mov     rdi, [rsp+150h+arg_8]
0x1800037af  mov     rbx, [rsp+150h+arg_10]
0x1800037b7  add     rsp, 130h
0x1800037be  pop     r15
0x1800037c0  pop     r14
0x1800037c2  pop     r13
0x1800037c4  pop     r12
0x1800037c6  pop     rbp
0x1800037c7  retn
```
