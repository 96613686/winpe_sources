# CXMLReader::ProcessNamespaceDcl(_XML_NODE_INFO * *,ulong)

- ea: `0x180026efc`
- end: `0x1800272ea`
- name: `?ProcessNamespaceDcl@CXMLReader@@AEAAJPEAPEAU_XML_NODE_INFO@@K@Z`
- size: `1006`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct _XML_NODE_INFO **, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024190`

## callees

- `0x180018874`
- `0x18001a6c8`
- `0x180023500`
- `0x180026efc`
- `0x18002867c`
- `0x180028700`
- `0x18002cd54`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180026f58`
- `msvcrt!_wcsnicmp` at `0x180026f93`
- `msvcrt!_wcsnicmp` at `0x180026fb0`
- `msvcrt!_wcsnicmp` at `0x180026fcd`
- `msvcrt!_wcsnicmp` at `0x180027186`
- `msvcrt!_wcsnicmp` at `0x18002719f`
- `msvcrt!_wcsnicmp` at `0x1800271b8`
- `msvcrt!_wcsnicmp` at `0x180026f58`
- `msvcrt!_wcsnicmp` at `0x180026f93`
- `msvcrt!_wcsnicmp` at `0x180026fb0`
- `msvcrt!_wcsnicmp` at `0x180026fcd`
- `msvcrt!_wcsnicmp` at `0x180027186`
- `msvcrt!_wcsnicmp` at `0x18002719f`
- `msvcrt!_wcsnicmp` at `0x1800271b8`

## string_xrefs

- `0x180026f4d`: `xmlns:`
- `0x180026fa5`: `urn:schemas-microsoft-com:xml-data`
- `0x180027194`: `urn:schemas-microsoft-com:datatypes`
- `0x180026fc2`: `urn:schemas-microsoft-com:rowset`

## pseudocode

```c
__int64 __fastcall CXMLReader::ProcessNamespaceDcl(CXMLReader *this, struct _XML_NODE_INFO **a2, unsigned int a3)
{
  unsigned int v3; // eax
  struct _XML_NODE_INFO **v4; // rbx
  unsigned int v6; // r12d
  __int64 v7; // r13
  struct _XML_NODE_INFO *v8; // rdi
  struct _XML_NODE_INFO *v9; // rbx
  unsigned int v10; // esi
  unsigned __int16 *v11; // r14
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  int v15; // ebx
  int v16; // eax
  int v17; // ebx
  int v18; // eax
  int v19; // ebx
  unsigned int v20; // edi
  ATL::CComBSTR *v21; // rbx
  int v22; // r8d
  const unsigned __int16 *v23; // rdx
  CCollectionList *v24; // rcx
  int appended; // eax
  int v26; // ebx
  int v27; // eax
  int v28; // ebx
  unsigned int v30; // [rsp+30h] [rbp-38h] BYREF

  v3 = a3;
  v4 = a2;
  v6 = 0;
  LODWORD(v7) = 1;
  while ( (unsigned int)v7 < v3 )
  {
    try
    {
      v8 = v4[(unsigned int)v7];
      if ( *((_DWORD *)v8 + 1) == 2 && !_wcsnicmp(*((const wchar_t **)v8 + 2), L"xmlns:", 6u) )
      {
        v7 = (unsigned int)(v7 + 1);
        v9 = v4[v7];
        v10 = ~*((_DWORD *)v8 + 7) + *((_DWORD *)v8 + 6);
        v11 = (unsigned __int16 *)(*((_QWORD *)v8 + 2) + 2 * (*((unsigned int *)v8 + 7) + 1LL));
        if ( _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_xmldata, *((unsigned int *)v9 + 6))
          && _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_Friendly_xmldata, *((unsigned int *)v9 + 6)) )
        {
          if ( _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_oledb, *((unsigned int *)v9 + 6)) )
          {
            if ( _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_dt, *((unsigned int *)v9 + 6))
              && _wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_Friendly_dt, *((unsigned int *)v9 + 6)) )
            {
              if ( !_wcsnicmp(*((const wchar_t **)v9 + 2), wsznsDef_schema, *((unsigned int *)v9 + 6)) )
              {
                v20 = 4;
                v21 = (CXMLReader *)((char *)this + 152);
                ATL::CComBSTR::Append((CXMLReader *)((char *)this + 152), v11, v10);
                v22 = 1;
                v23 = L":";
                goto LABEL_34;
              }
              v20 = 5;
            }
            else
            {
              v20 = 2;
            }
          }
          else
          {
            v12 = CXMLReader::AddReservedSymbol(this, v11, v10, 4);
            v13 = v12;
            if ( v12 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( off_180048D60[0] )
                  bidTraceW(off_180048208[0], 600064, off_180048D60[0], (unsigned int)v12, 586);
              }
              ThrowHR(v13);
            }
            v14 = CXMLReader::AddReservedSymbol(this, v11, v10, 7);
            v15 = v14;
            if ( v14 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048D58[0] )
                bidTraceW(off_180048208[0], 601088, off_180048D58[0], (unsigned int)v14, 587);
              ThrowHR(v15);
            }
            v16 = CXMLReader::AddReservedSymbol(this, v11, v10, 6);
            v17 = v16;
            if ( v16 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048D50[0] )
                bidTraceW(off_180048208[0], 602112, off_180048D50[0], (unsigned int)v16, 588);
              ThrowHR(v17);
            }
            v18 = CXMLReader::AddReservedSymbol(this, v11, v10, 5);
            v19 = v18;
            if ( v18 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048D48[0] )
                bidTraceW(off_180048208[0], 603136, off_180048D48[0], (unsigned int)v18, 589);
              ThrowHR(v19);
            }
            v20 = 3;
            v21 = (CXMLReader *)((char *)this + 144);
            ATL::CComBSTR::Append((CXMLReader *)((char *)this + 144), v11, v10);
            ATL::CComBSTR::Append((CXMLReader *)((char *)this + 144), L":", 1);
            v22 = 4;
            v23 = (const unsigned __int16 *)&wszData;
LABEL_34:
            ATL::CComBSTR::Append(v21, v23, v22);
          }
        }
        else
        {
          v20 = 1;
        }
        v24 = (CXMLReader *)((char *)this + 160);
        if ( v20 == 5 )
        {
          appended = CCollectionList::AppendDup(v24, v11, v10, 5u);
          v26 = appended;
          if ( appended < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048D40[0] )
              bidTraceW(off_180048208[0], 628736, off_180048D40[0], (unsigned int)appended, 614);
            ThrowHR(v26);
          }
        }
        else
        {
          v27 = CCollectionList::Append(v24, v11, v10, v20);
          v28 = v27;
          if ( v27 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 && off_180048D38[0] )
              bidTraceW(off_180048208[0], 632832, off_180048D38[0], (unsigned int)v27, 618);
            ThrowHR(v28);
          }
        }
        v4 = a2;
      }
      LODWORD(v7) = v7 + 1;
      v3 = a3;
    }
    catch ( long v30 )
    {
      return v30;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180026efc  mov     rax, rsp
0x180026eff  mov     [rax+8], rbx
0x180026f03  mov     [rax+20h], rsi
0x180026f07  mov     [rax+18h], r8d
0x180026f0b  mov     [rax+10h], rdx
0x180026f0f  push    rdi
0x180026f10  push    r12
0x180026f12  push    r13
0x180026f14  push    r14
0x180026f16  push    r15
0x180026f18  sub     rsp, 40h
0x180026f1c  mov     eax, r8d
0x180026f1f  mov     rbx, rdx
0x180026f22  mov     r15, rcx
0x180026f25  xor     r12d, r12d
0x180026f28  lea     r13d, [r12+1]
0x180026f2d  cmp     r13d, eax
0x180026f30  jnb     loc_1800272C3
0x180026f36  mov     eax, r13d
0x180026f39  mov     rdi, [rbx+rax*8]
0x180026f3d  cmp     dword ptr [rdi+4], 2
0x180026f41  jnz     loc_1800272B4
0x180026f47  mov     r8d, 6; MaxCount
0x180026f4d  lea     rdx, aXmlns; "xmlns:"
0x180026f54  mov     rcx, [rdi+10h]; String1
0x180026f58  call    cs:__imp__wcsnicmp
0x180026f5e  test    eax, eax
0x180026f60  jnz     loc_1800272B4
0x180026f66  inc     r13d
0x180026f69  mov     rbx, [rbx+r13*8]
0x180026f6d  mov     edx, [rdi+1Ch]
0x180026f70  mov     ecx, edx
0x180026f72  not     ecx
0x180026f74  mov     esi, [rdi+18h]
0x180026f77  add     esi, ecx
0x180026f79  mov     rax, [rdi+10h]
0x180026f7d  inc     rdx
0x180026f80  lea     r14, [rax+rdx*2]
0x180026f84  mov     r8d, [rbx+18h]; MaxCount
0x180026f88  lea     rdx, ?wsznsDef_xmldata@@3PAGA; "uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C148"...
0x180026f8f  mov     rcx, [rbx+10h]; String1
0x180026f93  call    cs:__imp__wcsnicmp
0x180026f99  test    eax, eax
0x180026f9b  jz      loc_1800271FD
0x180026fa1  mov     r8d, [rbx+18h]; MaxCount
0x180026fa5  lea     rdx, ?wsznsDef_Friendly_xmldata@@3PAGA; "urn:schemas-microsoft-com:xml-data"
0x180026fac  mov     rcx, [rbx+10h]; String1
0x180026fb0  call    cs:__imp__wcsnicmp
0x180026fb6  test    eax, eax
0x180026fb8  jz      loc_1800271FD
0x180026fbe  mov     r8d, [rbx+18h]; MaxCount
0x180026fc2  lea     rdx, ?wsznsDef_oledb@@3PAGA; "urn:schemas-microsoft-com:rowset"
0x180026fc9  mov     rcx, [rbx+10h]; String1
0x180026fcd  call    cs:__imp__wcsnicmp
0x180026fd3  test    eax, eax
0x180026fd5  jnz     loc_180027177
0x180026fdb  lea     r9d, [rax+4]
0x180026fdf  mov     r8d, esi
0x180026fe2  mov     rdx, r14
0x180026fe5  mov     rcx, r15
0x180026fe8  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x180026fed  mov     ebx, eax
0x180026fef  test    eax, eax
0x180026ff1  jns     short loc_180027032
0x180026ff3  test    byte ptr cs:_bidGblFlags, 2
0x180026ffa  jz      short loc_18002702B
0x180026ffc  mov     rcx, cs:off_180048D60; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027003  test    rcx, rcx
0x180027006  jz      short loc_18002702B
0x180027008  mov     [rsp+68h+var_48], 24Ah
0x180027010  mov     r9d, eax
0x180027013  mov     r8, cs:off_180048D60; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x18002701a  mov     edx, 92800h
0x18002701f  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027026  call    _bidTraceW
0x18002702b  mov     ecx, ebx; int
0x18002702d  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027032  mov     r9d, 7
0x180027038  mov     r8d, esi
0x18002703b  mov     rdx, r14
0x18002703e  mov     rcx, r15
0x180027041  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x180027046  mov     ebx, eax
0x180027048  test    eax, eax
0x18002704a  jns     short loc_18002708B
0x18002704c  test    byte ptr cs:_bidGblFlags, 2
0x180027053  jz      short loc_180027084
0x180027055  mov     rcx, cs:off_180048D58; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x18002705c  test    rcx, rcx
0x18002705f  jz      short loc_180027084
0x180027061  mov     [rsp+68h+var_48], 24Bh
0x180027069  mov     r9d, eax
0x18002706c  mov     r8, cs:off_180048D58; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027073  mov     edx, 92C00h
0x180027078  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002707f  call    _bidTraceW
0x180027084  mov     ecx, ebx; int
0x180027086  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002708b  mov     r9d, 6
0x180027091  mov     r8d, esi
0x180027094  mov     rdx, r14
0x180027097  mov     rcx, r15
0x18002709a  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x18002709f  mov     ebx, eax
0x1800270a1  test    eax, eax
0x1800270a3  jns     short loc_1800270E4
0x1800270a5  test    byte ptr cs:_bidGblFlags, 2
0x1800270ac  jz      short loc_1800270DD
0x1800270ae  mov     rcx, cs:off_180048D50; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x1800270b5  test    rcx, rcx
0x1800270b8  jz      short loc_1800270DD
0x1800270ba  mov     [rsp+68h+var_48], 24Ch
0x1800270c2  mov     r9d, eax
0x1800270c5  mov     r8, cs:off_180048D50; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x1800270cc  mov     edx, 93000h
0x1800270d1  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800270d8  call    _bidTraceW
0x1800270dd  mov     ecx, ebx; int
0x1800270df  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800270e4  mov     r9d, 5
0x1800270ea  mov     r8d, esi
0x1800270ed  mov     rdx, r14
0x1800270f0  mov     rcx, r15
0x1800270f3  call    ?AddReservedSymbol@CXMLReader@@AEAAJPEAGKW4SYMBOL_TYPE@@@Z; CXMLReader::AddReservedSymbol(ushort *,ulong,SYMBOL_TYPE)
0x1800270f8  mov     ebx, eax
0x1800270fa  test    eax, eax
0x1800270fc  jns     short loc_18002713D
0x1800270fe  test    byte ptr cs:_bidGblFlags, 2
0x180027105  jz      short loc_180027136
0x180027107  mov     rcx, cs:off_180048D48; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x18002710e  test    rcx, rcx
0x180027111  jz      short loc_180027136
0x180027113  mov     [rsp+68h+var_48], 24Dh
0x18002711b  mov     r9d, eax
0x18002711e  mov     r8, cs:off_180048D48; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027125  mov     edx, 93400h
0x18002712a  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027131  call    _bidTraceW
0x180027136  mov     ecx, ebx; int
0x180027138  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002713d  mov     edi, 3
0x180027142  lea     rbx, [r15+90h]
0x180027149  mov     r8d, esi; int
0x18002714c  mov     rdx, r14; unsigned __int16 *
0x18002714f  mov     rcx, rbx; this
0x180027152  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180027157  lea     r8d, [rdi-2]; int
0x18002715b  lea     rdx, asc_180039394; ":"
0x180027162  mov     rcx, rbx; this
0x180027165  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002716a  lea     r8d, [rdi+1]
0x18002716e  lea     rdx, ?wszData@@3PAGA; "data"
0x180027175  jmp     short loc_1800271E5
0x180027177  mov     r8d, [rbx+18h]; MaxCount
0x18002717b  lea     rdx, ?wsznsDef_dt@@3PAGA; "uuid:C2F41010-65B3-11d1-A29F-00AA00C148"...
0x180027182  mov     rcx, [rbx+10h]; String1
0x180027186  call    cs:__imp__wcsnicmp
0x18002718c  test    eax, eax
0x18002718e  jz      short loc_1800271F6
0x180027190  mov     r8d, [rbx+18h]; MaxCount
0x180027194  lea     rdx, ?wsznsDef_Friendly_dt@@3PAGA; "urn:schemas-microsoft-com:datatypes"
0x18002719b  mov     rcx, [rbx+10h]; String1
0x18002719f  call    cs:__imp__wcsnicmp
0x1800271a5  test    eax, eax
0x1800271a7  jz      short loc_1800271F6
0x1800271a9  mov     r8d, [rbx+18h]; MaxCount
0x1800271ad  lea     rdx, ?wsznsDef_schema@@3PAGA; "#RowsetSchema"
0x1800271b4  mov     rcx, [rbx+10h]; String1
0x1800271b8  call    cs:__imp__wcsnicmp
0x1800271be  test    eax, eax
0x1800271c0  jnz     short loc_1800271EF
0x1800271c2  lea     edi, [rax+4]
0x1800271c5  lea     rbx, [r15+98h]
0x1800271cc  mov     r8d, esi; int
0x1800271cf  mov     rdx, r14; unsigned __int16 *
0x1800271d2  mov     rcx, rbx; this
0x1800271d5  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800271da  lea     r8d, [rdi-3]; int
0x1800271de  lea     rdx, asc_180039394; ":"
0x1800271e5  mov     rcx, rbx; this
0x1800271e8  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800271ed  jmp     short loc_180027202
0x1800271ef  mov     edi, 5
0x1800271f4  jmp     short loc_180027202
0x1800271f6  mov     edi, 2
0x1800271fb  jmp     short loc_180027202
0x1800271fd  mov     edi, 1
0x180027202  lea     rcx, [r15+0A0h]; this
0x180027209  mov     r9d, edi; unsigned __int64
0x18002720c  mov     r8d, esi; unsigned int
0x18002720f  mov     rdx, r14; unsigned __int16 *
0x180027212  cmp     edi, 5
0x180027215  jnz     short loc_180027265
0x180027217  call    ?AppendDup@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::AppendDup(ushort *,ulong,unsigned __int64)
0x18002721c  mov     ebx, eax
0x18002721e  test    eax, eax
0x180027220  jns     loc_1800272AF
0x180027226  test    byte ptr cs:_bidGblFlags, 2
0x18002722d  jz      short loc_18002725E
0x18002722f  mov     rcx, cs:off_180048D40; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027236  test    rcx, rcx
0x180027239  jz      short loc_18002725E
0x18002723b  mov     [rsp+68h+var_48], 266h
0x180027243  mov     r9d, eax
0x180027246  mov     r8, cs:off_180048D40; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x18002724d  mov     edx, 99800h
0x180027252  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027259  call    _bidTraceW
0x18002725e  mov     ecx, ebx; int
0x180027260  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027265  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x18002726a  mov     ebx, eax
0x18002726c  test    eax, eax
0x18002726e  jns     short loc_1800272AF
0x180027270  test    byte ptr cs:_bidGblFlags, 2
0x180027277  jz      short loc_1800272A8
0x180027279  mov     rcx, cs:off_180048D38; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027280  test    rcx, rcx
0x180027283  jz      short loc_1800272A8
0x180027285  mov     [rsp+68h+var_48], 26Ah
0x18002728d  mov     r9d, eax
0x180027290  mov     r8, cs:off_180048D38; "<CXMLReader::ProcessNamespaceDcl|ADO|ER"...
0x180027297  mov     edx, 9A800h
0x18002729c  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800272a3  call    _bidTraceW
0x1800272a8  mov     ecx, ebx; int
0x1800272aa  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800272af  mov     rbx, [rsp+68h+arg_8]
0x1800272b4  inc     r13d
0x1800272b7  mov     eax, [rsp+68h+arg_10]
0x1800272be  jmp     loc_180026F2D
0x1800272c3  jmp     short loc_1800272CD
0x1800272c5  mov     r12d, [rsp+68h+arg_10]
0x1800272cd  mov     eax, r12d
0x1800272d0  lea     r11, [rsp+68h+var_28]
0x1800272d5  mov     rbx, [r11+30h]
0x1800272d9  mov     rsi, [r11+48h]
0x1800272dd  mov     rsp, r11
0x1800272e0  pop     r15
0x1800272e2  pop     r14
0x1800272e4  pop     r13
0x1800272e6  pop     r12
0x1800272e8  pop     rdi
0x1800272e9  retn
```
