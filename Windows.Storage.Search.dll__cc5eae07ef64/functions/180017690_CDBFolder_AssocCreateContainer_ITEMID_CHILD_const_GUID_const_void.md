# CDBFolder::_AssocCreateContainer(_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x180017690`
- end: `0x1800177bb`
- name: `?_AssocCreateContainer@CDBFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `299`
- prototype: `int(CDBFolder *__hidden this, const struct _ITEMID_CHILD *, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800171dc`
- `0x180017454`

## callees

- `0x1800191d0`
- `0x180071dc0`

## import_xrefs

- `Windows.Storage!AssocCreateForClasses` at `0x180017776`
- `Windows.Storage!AssocCreateForClasses` at `0x180017776`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001778c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017796`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001778c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017796`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDBFolder::_AssocCreateContainer(
        CDBFolder *this,
        const struct _ITEMID_CHILD *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned __int16 *v6; // rsi
  unsigned __int16 *v7; // rdi
  void *v8; // rbx
  unsigned __int16 *v10; // [rsp+30h] [rbp-89h] BYREF
  unsigned __int16 *v11; // [rsp+38h] [rbp-81h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-79h] BYREF
  ASSOCIATIONELEMENT rgClasses; // [rsp+50h] [rbp-69h] BYREF
  int v14; // [rsp+68h] [rbp-51h]
  __int64 v15; // [rsp+70h] [rbp-49h]
  unsigned __int16 *v16; // [rsp+78h] [rbp-41h]
  int v17; // [rsp+80h] [rbp-39h]
  __int64 v18; // [rsp+88h] [rbp-31h]
  LPVOID v19; // [rsp+90h] [rbp-29h]
  int v20; // [rsp+98h] [rbp-21h]
  __int64 v21; // [rsp+A0h] [rbp-19h]
  const wchar_t *v22; // [rsp+A8h] [rbp-11h]
  int v23; // [rsp+B0h] [rbp-9h]
  __int64 v24; // [rsp+B8h] [rbp-1h]
  __int64 v25; // [rsp+C0h] [rbp+7h]

  v10 = 0;
  v11 = 0;
  pv = 0;
  CDBFolder::GetContainerStackType((CDBFolder *)((char *)this + 184), a2, 0, &v10, &v11, (unsigned __int16 **)&pv);
  rgClasses.ac = ASSOCCLASS_FOLDER|ASSOCCLASS_PROGID_STR;
  rgClasses.hkClass = 0;
  v6 = v10;
  rgClasses.pszClass = v10;
  v14 = 10;
  v15 = 0;
  v7 = v11;
  v16 = v11;
  v17 = 10;
  v18 = 0;
  v8 = pv;
  v19 = pv;
  v20 = 10;
  v21 = 0;
  v22 = L"Stack";
  v23 = 8;
  v24 = 0;
  v25 = 0;
  LODWORD(a3) = AssocCreateForClasses(&rgClasses, 5u, a3, a4);
  CoTaskMemFree(v8);
  CoTaskMemFree(v7);
  CoTaskMemFree(v6);
  return (unsigned int)a3;
}

```

## disassembly

```asm
0x180017690  push    rbp
0x180017692  push    rbx
0x180017693  push    rsi
0x180017694  push    rdi
0x180017695  push    r14
0x180017697  push    r15
0x180017699  lea     rbp, [rsp-2Fh]
0x18001769e  sub     rsp, 0E8h
0x1800176a5  mov     rax, cs:__security_cookie
0x1800176ac  xor     rax, rsp
0x1800176af  mov     [rbp+57h+var_40], rax
0x1800176b3  mov     r15, r9
0x1800176b6  mov     r14, r8
0x1800176b9  mov     [rsp+110h+var_E0], 0
0x1800176c2  mov     [rsp+110h+var_D8], 0
0x1800176cb  mov     [rbp+57h+pv], 0
0x1800176d3  add     rcx, 0B8h; this
0x1800176da  lea     rax, [rbp+57h+pv]
0x1800176de  mov     [rsp+110h+var_E8], rax; unsigned __int16 **
0x1800176e3  lea     rax, [rsp+110h+var_D8]
0x1800176e8  mov     [rsp+110h+var_F0], rax; unsigned __int16 **
0x1800176ed  lea     r9, [rsp+110h+var_E0]; unsigned __int16 **
0x1800176f2  xor     r8d, r8d; bool
0x1800176f5  call    ?GetContainerStackType@CDBFolder@@UEAAXPEFBU_ITEMID_CHILD@@_NPEAPEAG22@Z; CDBFolder::GetContainerStackType(_ITEMID_CHILD const *,bool,ushort * *,ushort * *,ushort * *)
0x1800176fa  mov     eax, 0Ah
0x1800176ff  mov     [rbp+57h+rgClasses.ac], eax
0x180017702  mov     [rbp+57h+rgClasses.hkClass], 0
0x18001770a  mov     rsi, [rsp+110h+var_E0]
0x18001770f  mov     [rbp+57h+rgClasses.pszClass], rsi
0x180017713  mov     [rbp+57h+var_A8], eax
0x180017716  mov     [rbp+57h+var_A0], 0
0x18001771e  mov     rdi, [rsp+110h+var_D8]
0x180017723  mov     [rbp+57h+var_98], rdi
0x180017727  mov     [rbp+57h+var_90], eax
0x18001772a  mov     [rbp+57h+var_88], 0
0x180017732  mov     rbx, [rbp+57h+pv]
0x180017736  mov     [rbp+57h+var_80], rbx
0x18001773a  mov     [rbp+57h+var_78], eax
0x18001773d  mov     [rbp+57h+var_70], 0
0x180017745  lea     rax, aStack; "Stack"
0x18001774c  mov     [rbp+57h+var_68], rax
0x180017750  mov     [rbp+57h+var_60], 8
0x180017757  mov     [rbp+57h+var_58], 0
0x18001775f  mov     [rbp+57h+var_50], 0
0x180017767  mov     r9, r15; ppv
0x18001776a  mov     r8, r14; riid
0x18001776d  mov     edx, 5; cClasses
0x180017772  lea     rcx, [rbp+57h+rgClasses]; rgClasses
0x180017776  call    cs:__imp_AssocCreateForClasses
0x18001777c  mov     r14d, eax
0x18001777f  mov     rcx, rbx; pv
0x180017782  call    cs:__imp_CoTaskMemFree
0x180017788  nop
0x180017789  mov     rcx, rdi; pv
0x18001778c  call    cs:__imp_CoTaskMemFree
0x180017792  nop
0x180017793  mov     rcx, rsi; pv
0x180017796  call    cs:__imp_CoTaskMemFree
0x18001779c  mov     eax, r14d
0x18001779f  mov     rcx, [rbp+57h+var_40]
0x1800177a3  xor     rcx, rsp; StackCookie
0x1800177a6  call    __security_check_cookie
0x1800177ab  add     rsp, 0E8h
0x1800177b2  pop     r15
0x1800177b4  pop     r14
0x1800177b6  pop     rdi
0x1800177b7  pop     rsi
0x1800177b8  pop     rbx
0x1800177b9  pop     rbp
0x1800177ba  retn
```
