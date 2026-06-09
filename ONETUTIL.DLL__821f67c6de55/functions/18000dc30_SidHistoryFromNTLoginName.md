# SidHistoryFromNTLoginName

- ea: `0x18000dc30`
- end: `0x18000e08a`
- name: `SidHistoryFromNTLoginName`
- size: `1114`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation`

## callees

- `0x18000d394`
- `0x18000dc30`
- `0x1800838f0`
- `0x1800b10f0`
- `0x1800c0a00`
- `0x1800d9fd0`
- `0x1800da020`
- `0x180103634`
- `0x180103680`
- `0x1801503e0`
- `0x1801519a0`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x18000dca7`
- `KERNEL32!TlsGetValue` at `0x18000dffb`
- `KERNEL32!TlsGetValue` at `0x18000dca7`
- `KERNEL32!TlsGetValue` at `0x18000dffb`
- `ADVAPI32!GetLengthSid` at `0x18000decf`
- `ADVAPI32!GetLengthSid` at `0x18000decf`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000deb7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000df8f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000dfcc`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000deb7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000df8f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18000dfcc`
- `ACTIVEDS!ADsBuildVarArrayStr` at `0x18000dd1a`
- `ACTIVEDS!ADsBuildVarArrayStr` at `0x18000dd1a`
- `OLEAUT32!SysAllocString` at `0x18000dd80`
- `OLEAUT32!SysAllocString` at `0x18000dd80`
- `OLEAUT32!SysFreeString` at `0x18000e055`
- `OLEAUT32!SysFreeString` at `0x18000e055`
- `OLEAUT32!VariantInit` at `0x18000dc8d`
- `OLEAUT32!VariantInit` at `0x18000dc9b`
- `OLEAUT32!VariantInit` at `0x18000dc8d`
- `OLEAUT32!VariantInit` at `0x18000dc9b`
- `OLEAUT32!VariantClear` at `0x18000dd6a`
- `OLEAUT32!VariantClear` at `0x18000df52`
- `OLEAUT32!VariantClear` at `0x18000dfa1`
- `OLEAUT32!VariantClear` at `0x18000e024`
- `OLEAUT32!VariantClear` at `0x18000e032`
- `OLEAUT32!VariantClear` at `0x18000dd6a`
- `OLEAUT32!VariantClear` at `0x18000df52`
- `OLEAUT32!VariantClear` at `0x18000dfa1`
- `OLEAUT32!VariantClear` at `0x18000e024`
- `OLEAUT32!VariantClear` at `0x18000e032`
- `OLEAUT32!SafeArrayGetUBound` at `0x18000ddeb`
- `OLEAUT32!SafeArrayGetUBound` at `0x18000de5b`
- `OLEAUT32!SafeArrayGetUBound` at `0x18000ddeb`
- `OLEAUT32!SafeArrayGetUBound` at `0x18000de5b`
- `OLEAUT32!SafeArrayGetLBound` at `0x18000ddd3`
- `OLEAUT32!SafeArrayGetLBound` at `0x18000de73`
- `OLEAUT32!SafeArrayGetLBound` at `0x18000ddd3`
- `OLEAUT32!SafeArrayGetLBound` at `0x18000de73`
- `OLEAUT32!SafeArrayAccessData` at `0x18000de89`
- `OLEAUT32!SafeArrayAccessData` at `0x18000de89`
- `OLEAUT32!SafeArrayUnaccessData` at `0x18000df44`
- `OLEAUT32!SafeArrayUnaccessData` at `0x18000df44`
- `OLEAUT32!SafeArrayGetElement` at `0x18000de43`
- `OLEAUT32!SafeArrayGetElement` at `0x18000de43`

## string_xrefs

- `0x18000dcfd`: `sidHistory`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall SidHistoryFromNTLoginName(__int64 a1, VwstringVvector *a2)
{
  unsigned int v3; // ebx
  OLECHAR *v4; // r15
  VthreadContext *Value; // rax
  struct Vstatus *v6; // rax
  int v8; // eax
  __int64 v9; // r14
  int v10; // ebx
  BSTR v11; // rax
  SAFEARRAY *parray; // r13
  LONG v13; // edx
  LONG v14; // ecx
  SAFEARRAY *v15; // r12
  void *v16; // rbx
  DWORD LengthSid; // eax
  VthreadContext *v18; // rax
  struct Vstatus *v19; // rax
  LONG rgIndices; // [rsp+24h] [rbp-504h] BYREF
  LONG plLbound; // [rsp+28h] [rbp-500h] BYREF
  __int64 v22; // [rsp+30h] [rbp-4F8h] BYREF
  LONG plUbound; // [rsp+38h] [rbp-4F0h] BYREF
  int *v24; // [rsp+40h] [rbp-4E8h] BYREF
  BSTR v25; // [rsp+48h] [rbp-4E0h]
  VARIANTARG pvarg; // [rsp+50h] [rbp-4D8h] BYREF
  LONG v27; // [rsp+68h] [rbp-4C0h] BYREF
  LONG v28; // [rsp+6Ch] [rbp-4BCh] BYREF
  LPWSTR pPathNames; // [rsp+70h] [rbp-4B8h] BYREF
  void *ppvData; // [rsp+78h] [rbp-4B0h] BYREF
  VwstringVvector *v31; // [rsp+80h] [rbp-4A8h]
  VARIANTARG pv; // [rsp+88h] [rbp-4A0h] BYREF
  __int64 v33; // [rsp+A0h] [rbp-488h]
  VARIANTARG v34; // [rsp+B0h] [rbp-478h] BYREF
  void *Block; // [rsp+D0h] [rbp-458h] BYREF
  _BYTE v36[1028]; // [rsp+D8h] [rbp-450h] BYREF
  unsigned int v37; // [rsp+4DCh] [rbp-4Ch]
  int v38; // [rsp+4E0h] [rbp-48h]

  v33 = -2;
  v31 = a2;
  v3 = 0;
  v22 = 0;
  v4 = 0;
  v25 = 0;
  VariantInit(&pvarg);
  VariantInit(&pv);
  Value = (VthreadContext *)TlsGetValue(dwTlsIndex);
  v6 = VthreadContext::suspendImpersonation(Value);
  if ( v6 )
  {
    (**(void (__fastcall ***)(struct Vstatus *, __int64))v6)(v6, 1);
    return 0;
  }
  else
  {
    v8 = sub_18000D394(a1, &stru_180176A90, &v22);
    v9 = v22;
    if ( v8 >= 0 )
    {
      if ( v22 )
      {
        pPathNames = (LPWSTR)L"sidHistory";
        if ( ADsBuildVarArrayStr(&pPathNames, 1u, &pvarg) >= 0 )
        {
          v34 = pvarg;
          v10 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v9 + 152LL))(v9, &v34, 0);
          VariantClear(&pvarg);
          if ( v10 >= 0 )
          {
            v11 = SysAllocString(L"sidHistory");
            v4 = v11;
            v25 = v11;
            if ( v11 )
            {
              if ( (*(int (__fastcall **)(__int64, BSTR, VARIANTARG *))(*(_QWORD *)v9 + 136LL))(v9, v11, &pvarg) >= 0 )
              {
                parray = pvarg.parray;
                if ( SafeArrayGetLBound(pvarg.parray, 1u, &plLbound) < 0
                  || SafeArrayGetUBound(parray, 1u, &plUbound) < 0 )
                {
                  v3 = 0;
                }
                else
                {
                  Block = v36;
                  v37 = 0;
                  v38 = 512;
                  v13 = plLbound;
                  v14 = plLbound;
                  rgIndices = plLbound;
                  while ( v14 <= plUbound - v13 )
                  {
                    SafeArrayGetElement(parray, &rgIndices, &pv);
                    v15 = pv.parray;
                    if ( SafeArrayGetUBound(pv.parray, 1u, &v27) < 0 || SafeArrayGetLBound(v15, 1u, &v28) < 0 )
                    {
                      if ( Block != v36 )
                      {
                        if ( dword_1802B0018 )
                          COWSAllocator::Free(Block);
                        else
                          free(Block);
                      }
                      v3 = 0;
                      goto LABEL_35;
                    }
                    if ( SafeArrayAccessData(v15, &ppvData) < 0 )
                    {
                      if ( Block != v36 )
                      {
                        if ( dword_1802B0018 )
                          COWSAllocator::Free(Block);
                        else
                          free(Block);
                      }
                      v3 = 0;
                      goto LABEL_35;
                    }
                    v16 = ppvData;
                    LengthSid = GetLengthSid(ppvData);
                    VUserId::convertToString(v16, LengthSid, (struct VwstackBuffer512 *)&Block);
                    *((_WORD *)Block + v37) = 0;
                    v24 = &dword_1802B04A4;
                    Vwstring::Set((Vwstring *)&v24, (const wchar_t *)Block, 0xFFFFFFFF);
                    VwstringVvector::insert(v31, (const struct Vwstring *)&v24);
                    Vwstring::~Vwstring((Vwstring *)&v24);
                    v37 = 0;
                    SafeArrayUnaccessData(v15);
                    VariantClear(&pv);
                    v14 = ++rgIndices;
                    v13 = plLbound;
                  }
                  VariantClear(&pvarg);
                  if ( Block != v36 )
                  {
                    if ( dword_1802B0018 )
                      COWSAllocator::Free(Block);
                    else
                      free(Block);
                  }
                  v3 = 1;
                }
              }
              else
              {
                v3 = 0;
              }
            }
            else
            {
              v3 = 0;
            }
          }
          else
          {
            v3 = 0;
          }
        }
      }
    }
LABEL_35:
    v18 = (VthreadContext *)TlsGetValue(dwTlsIndex);
    v19 = VthreadContext::resumeImpersonation(v18);
    if ( v19 )
      (**(void (__fastcall ***)(struct Vstatus *, __int64))v19)(v19, 1);
    VariantClear(&pvarg);
    VariantClear(&pv);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    if ( v4 )
      SysFreeString(v4);
    return v3;
  }
}

```

## disassembly

```asm
0x18000dc30  mov     rax, rsp
0x18000dc33  push    rdi
0x18000dc34  push    r12
0x18000dc36  push    r13
0x18000dc38  push    r14
0x18000dc3a  push    r15
0x18000dc3c  sub     rsp, 500h
0x18000dc43  mov     qword ptr [rax-488h], 0FFFFFFFFFFFFFFFEh
0x18000dc4e  mov     [rax+18h], rbx
0x18000dc52  mov     [rax+20h], rsi
0x18000dc56  mov     rax, cs:__security_cookie
0x18000dc5d  xor     rax, rsp
0x18000dc60  mov     [rsp+528h+var_38], rax
0x18000dc68  mov     [rsp+528h+var_4A8], rdx
0x18000dc70  mov     rsi, rcx
0x18000dc73  xor     edi, edi
0x18000dc75  mov     ebx, edi
0x18000dc77  mov     [rsp+528h+var_508], ebx
0x18000dc7b  mov     [rsp+528h+var_4F8], rdi
0x18000dc80  mov     r15d, edi
0x18000dc83  mov     [rsp+528h+var_4E0], rdi
0x18000dc88  lea     rcx, [rsp+528h+pvarg]; pvarg
0x18000dc8d  call    cs:VariantInit
0x18000dc93  lea     rcx, [rsp+528h+pv]; pvarg
0x18000dc9b  call    cs:VariantInit
0x18000dca1  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000dca7  call    cs:TlsGetValue
0x18000dcad  mov     rcx, rax; this
0x18000dcb0  call    ?suspendImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::suspendImpersonation(void)
0x18000dcb5  mov     rcx, rax
0x18000dcb8  test    rax, rax
0x18000dcbb  jz      short loc_18000DCD3
0x18000dcbd  mov     rax, [rax]
0x18000dcc0  lea     edx, [rdi+1]
0x18000dcc3  mov     rax, [rax]
0x18000dcc6  call    cs:__guard_dispatch_icall_fptr
0x18000dccc  xor     eax, eax
0x18000dcce  jmp     loc_18000E05D
0x18000dcd3  lea     r8, [rsp+528h+var_4F8]
0x18000dcd8  lea     rdx, stru_180176A90
0x18000dcdf  mov     rcx, rsi
0x18000dce2  call    sub_18000D394
0x18000dce7  mov     r14, [rsp+528h+var_4F8]
0x18000dcec  test    eax, eax
0x18000dcee  js      loc_18000DFDD
0x18000dcf4  test    r14, r14
0x18000dcf7  jz      loc_18000DFDD
0x18000dcfd  lea     r12, aSidhistory; "sidHistory"
0x18000dd04  mov     [rsp+528h+pPathNames], r12
0x18000dd09  lea     r8, [rsp+528h+pvarg]; pVar
0x18000dd0e  mov     esi, 1
0x18000dd13  mov     edx, esi; dwPathNames
0x18000dd15  lea     rcx, [rsp+528h+pPathNames]; lppPathNames
0x18000dd1a  call    cs:ADsBuildVarArrayStr
0x18000dd20  test    eax, eax
0x18000dd22  jns     short loc_18000DD29
0x18000dd24  jmp     loc_18000DFF5
0x18000dd29  movups  xmm0, xmmword ptr [rsp+528h+pvarg]
0x18000dd2e  movaps  [rsp+528h+var_478], xmm0
0x18000dd36  movsd   xmm1, qword ptr [rsp+528h+pvarg+10h]
0x18000dd3c  movsd   [rsp+528h+var_468], xmm1
0x18000dd45  mov     rax, [r14]
0x18000dd48  xor     r8d, r8d
0x18000dd4b  lea     rdx, [rsp+528h+var_478]
0x18000dd53  mov     rcx, r14
0x18000dd56  mov     rax, [rax+98h]
0x18000dd5d  call    cs:__guard_dispatch_icall_fptr
0x18000dd63  mov     ebx, eax
0x18000dd65  lea     rcx, [rsp+528h+pvarg]; pvarg
0x18000dd6a  call    cs:VariantClear
0x18000dd70  test    ebx, ebx
0x18000dd72  jns     short loc_18000DD7D
0x18000dd74  mov     ebx, [rsp+528h+var_508]
0x18000dd78  jmp     loc_18000DFF5
0x18000dd7d  mov     rcx, r12; psz
0x18000dd80  call    cs:SysAllocString
0x18000dd86  mov     r15, rax
0x18000dd89  mov     [rsp+528h+var_4E0], rax
0x18000dd8e  test    rax, rax
0x18000dd91  jnz     short loc_18000DD9C
0x18000dd93  mov     ebx, [rsp+528h+var_508]
0x18000dd97  jmp     loc_18000DFF5
0x18000dd9c  mov     rax, [r14]
0x18000dd9f  lea     r8, [rsp+528h+pvarg]
0x18000dda4  mov     rdx, r15
0x18000dda7  mov     rcx, r14
0x18000ddaa  mov     rax, [rax+88h]
0x18000ddb1  call    cs:__guard_dispatch_icall_fptr
0x18000ddb7  test    eax, eax
0x18000ddb9  jns     short loc_18000DDC4
0x18000ddbb  mov     ebx, [rsp+528h+var_508]
0x18000ddbf  jmp     loc_18000DFF5
0x18000ddc4  mov     r13, qword ptr [rsp+528h+pvarg+8]
0x18000ddc9  lea     r8, [rsp+528h+plLbound]; plLbound
0x18000ddce  mov     edx, esi; nDim
0x18000ddd0  mov     rcx, r13; psa
0x18000ddd3  call    cs:SafeArrayGetLBound
0x18000ddd9  test    eax, eax
0x18000dddb  js      loc_18000DFD7
0x18000dde1  lea     r8, [rsp+528h+plUbound]; plUbound
0x18000dde6  mov     edx, esi; nDim
0x18000dde8  mov     rcx, r13; psa
0x18000ddeb  call    cs:SafeArrayGetUBound
0x18000ddf1  test    eax, eax
0x18000ddf3  js      loc_18000DFD7
0x18000ddf9  lea     rax, [rsp+528h+var_450]
0x18000de01  mov     [rsp+528h+Block], rax
0x18000de09  mov     [rsp+528h+var_4C], edi
0x18000de10  mov     [rsp+528h+var_48], 200h
0x18000de1b  mov     edx, [rsp+528h+plLbound]
0x18000de1f  mov     ecx, edx
0x18000de21  mov     [rsp+528h+rgIndices], edx
0x18000de25  mov     eax, [rsp+528h+plUbound]
0x18000de29  sub     eax, edx
0x18000de2b  cmp     ecx, eax
0x18000de2d  jg      loc_18000DF9C
0x18000de33  lea     r8, [rsp+528h+pv]; pv
0x18000de3b  lea     rdx, [rsp+528h+rgIndices]; rgIndices
0x18000de40  mov     rcx, r13; psa
0x18000de43  call    cs:SafeArrayGetElement
0x18000de49  mov     r12, qword ptr [rsp+528h+pv+8]
0x18000de51  lea     r8, [rsp+528h+var_4C0]; plUbound
0x18000de56  mov     edx, esi; nDim
0x18000de58  mov     rcx, r12; psa
0x18000de5b  call    cs:SafeArrayGetUBound
0x18000de61  test    eax, eax
0x18000de63  js      loc_18000DF6B
0x18000de69  lea     r8, [rsp+528h+var_4BC]; plLbound
0x18000de6e  mov     edx, esi; nDim
0x18000de70  mov     rcx, r12; psa
0x18000de73  call    cs:SafeArrayGetLBound
0x18000de79  test    eax, eax
0x18000de7b  js      loc_18000DF6B
0x18000de81  lea     rdx, [rsp+528h+ppvData]; ppvData
0x18000de86  mov     rcx, r12; psa
0x18000de89  call    cs:SafeArrayAccessData
0x18000de8f  test    eax, eax
0x18000de91  jns     short loc_18000DEC7
0x18000de93  lea     rax, [rsp+528h+var_450]
0x18000de9b  mov     rcx, [rsp+528h+Block]; void *
0x18000dea3  cmp     rcx, rax
0x18000dea6  jz      short loc_18000DEBE
0x18000dea8  cmp     cs:dword_1802B0018, edi
0x18000deae  jz      short loc_18000DEB7
0x18000deb0  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18000deb5  jmp     short loc_18000DEBE
0x18000deb7  call    cs:free
0x18000debd  nop
0x18000debe  mov     ebx, [rsp+528h+var_508]
0x18000dec2  jmp     loc_18000DFF5
0x18000dec7  mov     rbx, [rsp+528h+ppvData]
0x18000decc  mov     rcx, rbx; pSid
0x18000decf  call    cs:GetLengthSid
0x18000ded5  mov     edx, eax; unsigned int
0x18000ded7  lea     r8, [rsp+528h+Block]; struct VwstackBuffer512 *
0x18000dedf  mov     rcx, rbx; void *
0x18000dee2  call    ?convertToString@VUserId@@SAXPEAXKAEAVVwstackBuffer512@@@Z; VUserId::convertToString(void *,ulong,VwstackBuffer512 &)
0x18000dee7  mov     ecx, [rsp+528h+var_4C]
0x18000deee  mov     rax, [rsp+528h+Block]
0x18000def6  mov     [rax+rcx*2], di
0x18000defa  lea     rax, dword_1802B04A4
0x18000df01  mov     [rsp+528h+var_4E8], rax
0x18000df06  or      r8d, 0FFFFFFFFh; unsigned int
0x18000df0a  mov     rdx, [rsp+528h+Block]; wchar_t *
0x18000df12  lea     rcx, [rsp+528h+var_4E8]; this
0x18000df17  call    ?Set@Vwstring@@QEAAXPEB_WK@Z; Vwstring::Set(wchar_t const *,ulong)
0x18000df1c  nop
0x18000df1d  lea     rdx, [rsp+528h+var_4E8]; struct Vwstring *
0x18000df22  mov     rcx, [rsp+528h+var_4A8]; this
0x18000df2a  call    ?insert@VwstringVvector@@QEAAXAEBVVwstring@@@Z; VwstringVvector::insert(Vwstring const &)
0x18000df2f  nop
0x18000df30  lea     rcx, [rsp+528h+var_4E8]; this
0x18000df35  call    ??1Vwstring@@QEAA@XZ_0; Vwstring::~Vwstring(void)
0x18000df3a  mov     [rsp+528h+var_4C], edi
0x18000df41  mov     rcx, r12; psa
0x18000df44  call    cs:SafeArrayUnaccessData
0x18000df4a  lea     rcx, [rsp+528h+pv]; pvarg
0x18000df52  call    cs:VariantClear
0x18000df58  mov     ecx, [rsp+528h+rgIndices]
0x18000df5c  add     ecx, esi
0x18000df5e  mov     [rsp+528h+rgIndices], ecx
0x18000df62  mov     edx, [rsp+528h+plLbound]
0x18000df66  jmp     loc_18000DE25
0x18000df6b  lea     rax, [rsp+528h+var_450]
0x18000df73  mov     rcx, [rsp+528h+Block]; void *
0x18000df7b  cmp     rcx, rax
0x18000df7e  jz      short loc_18000DF96
0x18000df80  cmp     cs:dword_1802B0018, edi
0x18000df86  jz      short loc_18000DF8F
0x18000df88  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18000df8d  jmp     short loc_18000DF96
0x18000df8f  call    cs:free
0x18000df95  nop
0x18000df96  mov     ebx, [rsp+528h+var_508]
0x18000df9a  jmp     short loc_18000DFF5
0x18000df9c  lea     rcx, [rsp+528h+pvarg]; pvarg
0x18000dfa1  call    cs:VariantClear
0x18000dfa7  nop
0x18000dfa8  lea     rax, [rsp+528h+var_450]
0x18000dfb0  mov     rcx, [rsp+528h+Block]; void *
0x18000dfb8  cmp     rcx, rax
0x18000dfbb  jz      short loc_18000DFD3
0x18000dfbd  cmp     cs:dword_1802B0018, edi
0x18000dfc3  jz      short loc_18000DFCC
0x18000dfc5  call    ?Free@COWSAllocator@@SAXPEAX@Z; COWSAllocator::Free(void *)
0x18000dfca  jmp     short loc_18000DFD3
0x18000dfcc  call    cs:free
0x18000dfd2  nop
0x18000dfd3  mov     ebx, esi
0x18000dfd5  jmp     short loc_18000DFF5
0x18000dfd7  mov     ebx, [rsp+528h+var_508]
0x18000dfdb  jmp     short loc_18000DFF5
0x18000dfdd  mov     esi, 1
0x18000dfe2  jmp     short loc_18000DFF5
0x18000dfe4  xor     edi, edi
0x18000dfe6  lea     esi, [rdi+1]
0x18000dfe9  mov     ebx, edi
0x18000dfeb  mov     r14, [rsp+528h+var_4F8]
0x18000dff0  mov     r15, [rsp+528h+var_4E0]
0x18000dff5  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000dffb  call    cs:TlsGetValue
0x18000e001  mov     rcx, rax; this
0x18000e004  call    ?resumeImpersonation@VthreadContext@@QEAAPEAVVstatus@@XZ; VthreadContext::resumeImpersonation(void)
0x18000e009  mov     rcx, rax
0x18000e00c  test    rax, rax
0x18000e00f  jz      short loc_18000E01F
0x18000e011  mov     rax, [rax]
0x18000e014  mov     edx, esi
0x18000e016  mov     rax, [rax]
0x18000e019  call    cs:__guard_dispatch_icall_fptr
0x18000e01f  lea     rcx, [rsp+528h+pvarg]; pvarg
0x18000e024  call    cs:VariantClear
0x18000e02a  lea     rcx, [rsp+528h+pv]; pvarg
0x18000e032  call    cs:VariantClear
0x18000e038  test    r14, r14
0x18000e03b  jz      short loc_18000E04D
0x18000e03d  mov     rdx, [r14]
0x18000e040  mov     rcx, r14
0x18000e043  mov     rax, [rdx+10h]
0x18000e047  call    cs:__guard_dispatch_icall_fptr
0x18000e04d  test    r15, r15
0x18000e050  jz      short loc_18000E05B
0x18000e052  mov     rcx, r15; bstrString
0x18000e055  call    cs:SysFreeString
0x18000e05b  mov     eax, ebx
0x18000e05d  mov     rcx, [rsp+528h+var_38]
0x18000e065  xor     rcx, rsp
0x18000e068  call    sub_1801503E0
0x18000e06d  lea     r11, [rsp+528h+var_28]
0x18000e075  mov     rbx, [r11+40h]
0x18000e079  mov     rsi, [r11+48h]
0x18000e07d  mov     rsp, r11
0x18000e080  pop     r15
0x18000e082  pop     r14
0x18000e084  pop     r13
0x18000e086  pop     r12
0x18000e088  pop     rdi
0x18000e089  retn
```
