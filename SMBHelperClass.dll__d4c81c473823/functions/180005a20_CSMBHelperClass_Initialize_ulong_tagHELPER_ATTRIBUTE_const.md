# CSMBHelperClass::Initialize(ulong,tagHELPER_ATTRIBUTE * const)

- ea: `0x180005a20`
- end: `0x180005d3d`
- name: `?Initialize@CSMBHelperClass@@UEAAJKQEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(CSMBHelperClass *__hidden this, unsigned int, struct tagHELPER_ATTRIBUTE *const)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000257c`
- `0x180005a20`
- `0x18000a060`
- `0x18000d750`
- `0x18000dd04`
- `0x18000e010`
- `0x18000e10c`
- `0x18000e3b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005cfc`

## string_xrefs

- `0x180005b4a`: `UNCPath`
- `0x180005b75`: `UNCPath`
- `0x180005cc5`: `UNCPath`
- `0x180005c57`: `SharePath`
- `0x180005c84`: `ShareName`
- `0x180005c99`: `ServerPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSMBHelperClass::Initialize(
        CSMBHelperClass *this,
        unsigned int a2,
        struct tagHELPER_ATTRIBUTE *const a3)
{
  CSMBHelperClass *v4; // rsi
  AttributeList *v5; // r14
  AttributeList *v6; // r12
  unsigned int v7; // r13d
  __int64 *v8; // rbx
  AttributeList *v9; // r13
  __int64; // rax
  __int64 v11; // rcx
  __int64 v12; // r13
  __int64 v13; // rbx
  __int64 Attribute; // rax
  unsigned __int16 ***v15; // r14
  unsigned __int16 **v16; // r9
  __int64 v17; // rax
  unsigned __int16 *v18; // r8
  unsigned __int64 v19; // rcx
  unsigned int v20; // edx
  unsigned __int16 *v21; // rcx
  unsigned __int64 v22; // rdx
  unsigned __int16 *v23; // r15
  unsigned __int16 *v24; // rbx
  int pExceptionObject; // [rsp+20h] [rbp-B8h] BYREF
  int v26; // [rsp+24h] [rbp-B4h] BYREF
  int v27; // [rsp+28h] [rbp-B0h] BYREF
  AttributeList *v28; // [rsp+30h] [rbp-A8h]
  AttributeList *v29; // [rsp+40h] [rbp-98h]
  AttributeList *v30; // [rsp+48h] [rbp-90h]
  _BYTE v31[24]; // [rsp+50h] [rbp-88h] BYREF
  _BYTE v32[24]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v33[88]; // [rsp+80h] [rbp-58h] BYREF
  unsigned __int16 *v35; // [rsp+E0h] [rbp+8h]
  unsigned int v36; // [rsp+E8h] [rbp+10h]
  int v37; // [rsp+F8h] [rbp+20h]

  v36 = a2;
  v4 = this;
  if ( *((_DWORD *)this + 70) || _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 1, 0) )
    goto LABEL_16;
  v5 = (CSMBHelperClass *)((char *)this + 208);
  v28 = (CSMBHelperClass *)((char *)this + 208);
  v30 = (CSMBHelperClass *)((char *)this + 208);
  v29 = (CSMBHelperClass *)((char *)this + 208);
  v6 = (CSMBHelperClass *)((char *)this + 208);
  v37 = 0;
  v7 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    while ( v7 < a2 )
    {
      if ( a3[v7].type == AT_UINT32 )
      {
        AttributeList::setDWordAttribute(v5, a3[v7].pwszName, a3[v7].DWord);
      }
      else if ( a3[v7].type == AT_STRING )
      {
        AttributeList::setStringAttribute(v5, a3[v7].pwszName, a3[v7].PWStr);
      }
      else
      {
        v37 = 1;
      }
      ++v7;
      a2 = v36;
    }
    if ( v37 )
    {
      pExceptionObject = 9;
      throw (TestException *)&pExceptionObject;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &enum TestException `RTTI Type Descriptor', (TestException *)&v26) )
    {
      if ( v26 != 4 )
      {
         = 2147500037LL;
        __eh34_try_continuation(0, &enum TestException `RTTI Type Descriptor', &loc_180005AEA);
        goto LABEL_69;
      }
      v4 = this;
      v5 = v28;
      v6 = v28;
      __eh34_try_continuation(0, &enum TestException `RTTI Type Descriptor', &loc_180005AF1);
    }
  }
  v8 = (__int64 *)*((_QWORD *)v4 + 29);
  v9 = v29;
  while ( 1 )
  {
    v8 = (__int64 *)*v8;
    if ( v8 == *((__int64 **)v4 + 29) )
      break;
    if ( !(unsigned int)AttributeList::attributeExists(v9, (unsigned __int16 *)v8[2]) )
      goto LABEL_16;
  }
  v11 = *(_QWORD *)(AttributeList::getAttribute(v5, v31, L"UNCPath", 1) + 8);
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( *(_WORD *)(v11 + 2 * v13) );
  Attribute = AttributeList::getAttribute(v5, v32, L"UNCPath", 1);
  v15 = (unsigned __int16 ***)((char *)v4 + 248);
  if ( (unsigned int)SplitUNCPath(*(_WORD **)(Attribute + 8), (int)v13 + 1, (__int64)v4 + 248) )
    goto LABEL_16;
  v16 = *v15;
  v17 = *((_QWORD *)v4 + 32) - (_QWORD)*v15;
  if ( !v17 )
    goto LABEL_16;
  if ( v17 == 8 )
  {
    v18 = *v16;
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    if ( v19 >= 3 && *v18 == 92 && v18[1] == 92 )
    {
      v20 = 2;
      while ( v18[v20] != 92 )
      {
        if ( ++v20 >= v19 )
        {
          *((_DWORD *)v4 + 71) = 1;
          goto LABEL_31;
        }
      }
    }
    goto LABEL_16;
  }
LABEL_31:
  v21 = *v16;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  v23 = 0;
  if ( v22 >= 3 )
    v23 = v21 + 2;
  if ( !v23 )
  {
LABEL_16:
     = 2147500037LL;
    goto LABEL_69;
  }
  if ( __eh34_try(-1, 2) )
  {
    __eh34_scope_strut(2);
    v24 = AllocateAndCatStrings(v21, L"\\IPC$");
    v35 = v24;
  }
  if ( __eh34_catch(2) )
  {
    if ( __eh34_catch_type(2, &enum TestException `RTTI Type Descriptor', 0) )
    {
       = 2147942414LL;
      __eh34_try_continuation(2, &enum TestException `RTTI Type Descriptor', &loc_180005D18);
      goto LABEL_69;
    }
  }
  if ( __eh34_try(-1, 4) )
  {
    __eh34_scope_strut(4);
    if ( !*((_DWORD *)v4 + 71) )
    {
      AttributeList::setStringAttribute(v30, L"SharePath", (*v15)[1]);
      do
        ++v12;
      while ( (**v15)[v12] );
      AttributeList::setStringAttribute(v6, L"ShareName", &(*v15)[1][v12 + 1]);
    }
    AttributeList::setStringAttribute(v6, L"ServerPath", **v15);
    AttributeList::setStringAttribute(v6, L"ServerIPCUNC", v24);
    if ( *((_DWORD *)v4 + 71) )
      AttributeList::setStringAttribute(v6, L"UNCPath", v24);
    AttributeList::setStringAttribute(v6, L"ServerName", v23);
    AttributeList::setDWordAttribute(v6, L"DFSShare", 0);
  }
  if ( __eh34_catch(4) )
  {
    if ( __eh34_catch_type(4, &enum TestException `RTTI Type Descriptor', (TestException *)&v27) )
    {
      CoTaskMemFree(v35);
      if ( v27 )
      {
         = 2147500037LL;
        __eh34_try_continuation(4, &enum TestException `RTTI Type Descriptor', &loc_180005D13);
      }
      else
      {
         = 2147942414LL;
        __eh34_try_continuation(4, &enum TestException `RTTI Type Descriptor', &loc_180005D09);
      }
LABEL_69:
      ;
    }
    if ( __eh34_catch_type(4, &exception `RTTI Type Descriptor', (exception *)v33) )
    {
      CoTaskMemFree(v35);
      exception::~exception((exception *)v33);
       = 2147500037LL;
      __eh34_try_continuation(4, &exception `RTTI Type Descriptor', &loc_180005AEA);
      goto LABEL_69;
    }
  }
  CoTaskMemFree(v24);
   = 0;
  goto LABEL_69;
}

```

## disassembly

```asm
0x180005a20  mov     [rsp+arg_8], edx
0x180005a24  mov     [rsp+arg_0], rcx
0x180005a29  push    rbx
0x180005a2a  push    rsi
0x180005a2b  push    rdi
0x180005a2c  push    r12
0x180005a2e  push    r13
0x180005a30  push    r14
0x180005a32  push    r15
0x180005a34  sub     rsp, 0A0h
0x180005a3b  mov     rbx, r8
0x180005a3e  mov     rsi, rcx
0x180005a41  xor     edi, edi
0x180005a43  cmp     [rcx+118h], edi
0x180005a49  jnz     loc_180005B2F
0x180005a4f  xor     eax, eax
0x180005a51  lea     r15d, [rdi+1]
0x180005a55  lock cmpxchg [rcx+10h], r15d
0x180005a5b  jnz     loc_180005B2F
0x180005a61  lea     r14, [rcx+0D0h]
0x180005a68  mov     [rsp+0D8h+var_A8], r14
0x180005a6d  mov     [rsp+0D8h+var_90], r14
0x180005a72  mov     [rsp+0D8h+var_98], r14
0x180005a77  mov     r12, r14
0x180005a7a  mov     [rsp+0D8h+arg_18], edi
0x180005a81  mov     r13d, edi
0x180005a84  cmp     r13d, edx
0x180005a87  jnb     short loc_180005ADB
0x180005a89  mov     eax, r13d
0x180005a8c  lea     rdx, [rax+rax*8]
0x180005a90  add     rdx, rdx
0x180005a93  cmp     dword ptr [rbx+rdx*8+8], 7
0x180005a98  jz      short loc_180005ABE
0x180005a9a  cmp     dword ptr [rbx+rdx*8+8], 0Ah
0x180005a9f  jz      short loc_180005AAB
0x180005aa1  mov     [rsp+0D8h+arg_18], r15d
0x180005aa9  jmp     short loc_180005ACF
0x180005aab  mov     r8, [rbx+rdx*8+10h]; unsigned __int16 *
0x180005ab0  mov     rdx, [rbx+rdx*8]; unsigned __int16 *
0x180005ab4  mov     rcx, r14; this
0x180005ab7  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005abc  jmp     short loc_180005ACF
0x180005abe  mov     r8d, [rbx+rdx*8+10h]; unsigned int
0x180005ac3  mov     rdx, [rbx+rdx*8]; unsigned __int16 *
0x180005ac7  mov     rcx, r14; this
0x180005aca  call    ?setDWordAttribute@AttributeList@@QEAAXPEAGK@Z; AttributeList::setDWordAttribute(ushort *,ulong)
0x180005acf  add     r13d, r15d
0x180005ad2  mov     edx, [rsp+0D8h+arg_8]
0x180005ad9  jmp     short loc_180005A84
0x180005adb  cmp     [rsp+0D8h+arg_18], edi
0x180005ae2  jnz     loc_180005D22
0x180005ae8  jmp     short loc_180005B07
0x180005aea  mov     eax, 80004005h
0x180005aef  jmp     short loc_180005B34
0x180005af1  xor     edi, edi
0x180005af3  lea     r15d, [rdi+1]
0x180005af7  mov     rsi, [rsp+0D8h+arg_0]
0x180005aff  mov     r14, [rsp+0D8h+var_A8]
0x180005b04  mov     r12, r14
0x180005b07  mov     rbx, [rsi+0E8h]
0x180005b0e  mov     r13, [rsp+0D8h+var_98]
0x180005b13  mov     rbx, [rbx]
0x180005b16  cmp     rbx, [rsi+0E8h]
0x180005b1d  jz      short loc_180005B47
0x180005b1f  mov     rdx, [rbx+10h]; unsigned __int16 *
0x180005b23  mov     rcx, r13; this
0x180005b26  call    ?attributeExists@AttributeList@@QEAAHPEAG@Z; AttributeList::attributeExists(ushort *)
0x180005b2b  test    eax, eax
0x180005b2d  jnz     short loc_180005B13
0x180005b2f  mov     eax, 80004005h
0x180005b34  add     rsp, 0A0h
0x180005b3b  pop     r15
0x180005b3d  pop     r14
0x180005b3f  pop     r13
0x180005b41  pop     r12
0x180005b43  pop     rdi
0x180005b44  pop     rsi
0x180005b45  pop     rbx
0x180005b46  retn
0x180005b47  mov     r9d, r15d
0x180005b4a  lea     r8, aUncpath; "UNCPath"
0x180005b51  lea     rdx, [rsp+0D8h+var_88]
0x180005b56  mov     rcx, r14
0x180005b59  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x180005b5e  mov     rcx, [rax+8]
0x180005b62  or      r13, 0FFFFFFFFFFFFFFFFh
0x180005b66  mov     rbx, r13
0x180005b69  inc     rbx
0x180005b6c  cmp     [rcx+rbx*2], di
0x180005b70  jnz     short loc_180005B69
0x180005b72  mov     r9d, r15d
0x180005b75  lea     r8, aUncpath; "UNCPath"
0x180005b7c  lea     rdx, [rsp+0D8h+var_70]
0x180005b81  mov     rcx, r14
0x180005b84  call    ?getAttribute@AttributeList@@QEAA?AUAttribute@@PEAGW4AttributeType@@@Z; AttributeList::getAttribute(ushort *,AttributeType)
0x180005b89  lea     r14, [rsi+0F8h]
0x180005b90  mov     r8, r14
0x180005b93  lea     edx, [rbx+1]
0x180005b96  mov     rcx, [rax+8]
0x180005b9a  call    ?SplitUNCPath@@YA?AW4SMBHC_ResultCode@@PEAGKAEAV?$vector@PEAGV?$allocator@PEAG@std@@@std@@@Z; SplitUNCPath(ushort *,ulong,std::vector<ushort *> &)
0x180005b9f  test    eax, eax
0x180005ba1  jnz     short loc_180005B2F
0x180005ba3  mov     r9, [r14]
0x180005ba6  mov     rax, [r14+8]
0x180005baa  sub     rax, r9
0x180005bad  jz      short loc_180005B2F
0x180005baf  cmp     rax, 8
0x180005bb3  jnz     short loc_180005C0A
0x180005bb5  mov     r8, [r9]
0x180005bb8  mov     rcx, r13
0x180005bbb  inc     rcx
0x180005bbe  cmp     [r8+rcx*2], di
0x180005bc3  jnz     short loc_180005BBB
0x180005bc5  cmp     rcx, 3
0x180005bc9  jb      loc_180005B2F
0x180005bcf  cmp     word ptr [r8], 5Ch ; '\'
0x180005bd4  jnz     loc_180005B2F
0x180005bda  cmp     word ptr [r8+2], 5Ch ; '\'
0x180005be0  jnz     loc_180005B2F
0x180005be6  mov     edx, 2
0x180005beb  mov     eax, edx
0x180005bed  cmp     word ptr [r8+rax*2], 5Ch ; '\'
0x180005bf3  jz      loc_180005B2F
0x180005bf9  add     edx, r15d
0x180005bfc  mov     eax, edx
0x180005bfe  cmp     rax, rcx
0x180005c01  jb      short loc_180005BEB
0x180005c03  mov     [rsi+11Ch], r15d
0x180005c0a  mov     rcx, [r9]; unsigned __int16 *
0x180005c0d  mov     rdx, r13
0x180005c10  inc     rdx
0x180005c13  cmp     [rcx+rdx*2], di
0x180005c17  jnz     short loc_180005C10
0x180005c19  lea     rax, [rcx+4]
0x180005c1d  mov     r15, rdi
0x180005c20  cmp     rdx, 3
0x180005c24  cmovnb  r15, rax
0x180005c28  test    r15, r15
0x180005c2b  jz      loc_180005B2F
0x180005c31  lea     rdx, aIpc; "\\IPC$"
0x180005c38  call    ?AllocateAndCatStrings@@YAPEAGPEAG0@Z; AllocateAndCatStrings(ushort *,ushort *)
0x180005c3d  mov     rbx, rax
0x180005c40  mov     [rsp+0D8h+arg_0], rax
0x180005c48  cmp     [rsi+11Ch], edi
0x180005c4e  jnz     short loc_180005C93
0x180005c50  mov     r8, [r14]
0x180005c53  mov     r8, [r8+8]; unsigned __int16 *
0x180005c57  lea     rdx, aSharepath; "SharePath"
0x180005c5e  mov     rcx, [rsp+0D8h+var_90]; this
0x180005c63  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005c68  mov     rax, [r14]
0x180005c6b  mov     rcx, [rax]
0x180005c6e  inc     r13
0x180005c71  cmp     [rcx+r13*2], di
0x180005c76  jnz     short loc_180005C6E
0x180005c78  mov     r8, [rax+8]
0x180005c7c  add     r8, 2
0x180005c80  lea     r8, [r8+r13*2]; unsigned __int16 *
0x180005c84  lea     rdx, aSharename; "ShareName"
0x180005c8b  mov     rcx, r12; this
0x180005c8e  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005c93  mov     r8, [r14]
0x180005c96  mov     r8, [r8]; unsigned __int16 *
0x180005c99  lea     rdx, aServerpath; "ServerPath"
0x180005ca0  mov     rcx, r12; this
0x180005ca3  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005ca8  mov     r8, rbx; unsigned __int16 *
0x180005cab  lea     rdx, aServeripcunc; "ServerIPCUNC"
0x180005cb2  mov     rcx, r12; this
0x180005cb5  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005cba  cmp     [rsi+11Ch], edi
0x180005cc0  jz      short loc_180005CD4
0x180005cc2  mov     r8, rbx; unsigned __int16 *
0x180005cc5  lea     rdx, aUncpath; "UNCPath"
0x180005ccc  mov     rcx, r12; this
0x180005ccf  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005cd4  mov     r8, r15; unsigned __int16 *
0x180005cd7  lea     rdx, aServername; "ServerName"
0x180005cde  mov     rcx, r12; this
0x180005ce1  call    ?setStringAttribute@AttributeList@@QEAAXPEAG0@Z; AttributeList::setStringAttribute(ushort *,ushort *)
0x180005ce6  xor     r8d, r8d; unsigned int
0x180005ce9  lea     rdx, aDfsshare; "DFSShare"
0x180005cf0  mov     rcx, r12; this
0x180005cf3  call    ?setDWordAttribute@AttributeList@@QEAAXPEAGK@Z; AttributeList::setDWordAttribute(ushort *,ulong)
0x180005cf8  nop
0x180005cf9  mov     rcx, rbx; pv
0x180005cfc  call    cs:__imp_CoTaskMemFree
0x180005d02  xor     eax, eax
0x180005d04  jmp     loc_180005B34
0x180005d09  mov     eax, 8007000Eh
0x180005d0e  jmp     loc_180005AEF
0x180005d13  jmp     loc_180005AEA
0x180005d18  mov     eax, 8007000Eh
0x180005d1d  jmp     loc_180005B34
0x180005d22  mov     [rsp+0D8h+pExceptionObject], 9
0x180005d2a  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x180005d31  lea     rcx, [rsp+0D8h+pExceptionObject]; pExceptionObject
0x180005d36  call    _CxxThrowException_0
```
