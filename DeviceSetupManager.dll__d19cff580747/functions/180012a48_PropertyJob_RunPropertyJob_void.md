# PropertyJob::_RunPropertyJob(void)

- ea: `0x180012a48`
- end: `0x180012cb4`
- name: `?_RunPropertyJob@PropertyJob@@AEAAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(PropertyJob *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180033d80`

## callees

- `0x180002a24`
- `0x180005ed0`
- `0x1800070a0`
- `0x18000fa88`
- `0x1800112a4`
- `0x180011fdc`
- `0x1800128ac`
- `0x180012a48`
- `0x18001370c`
- `0x180013d78`
- `0x180018170`
- `0x180033208`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012bbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c74`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012bbd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180012c74`

## string_xrefs

- `0x180012aa7`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`
- `0x180012b29`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`
- `0x180012ba7`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PropertyJob::_RunPropertyJob(PropertyJob *this)
{
  RTL_SRWLOCK *v2; // r15
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v6; // rax
  const OLECHAR *v7; // rbx
  char *v8; // rdx
  int v9; // eax
  unsigned int v10; // esi
  int DevnodeList; // eax
  __int64 i; // rbx
  int v13; // [rsp+20h] [rbp-39h]
  __int64 v14; // [rsp+30h] [rbp-29h] BYREF
  std::_Ref_count_base *v15; // [rsp+38h] [rbp-21h]
  RTL_SRWLOCK *v16; // [rsp+40h] [rbp-19h] BYREF
  std::_Ref_count_base *v17; // [rsp+48h] [rbp-11h]
  _BYTE v18[16]; // [rsp+50h] [rbp-9h] BYREF
  PROPVARIANT pvar[2]; // [rsp+60h] [rbp+7h] BYREF
  __int64 v20; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  char v22; // [rsp+C0h] [rbp+67h] BYREF

  Job::GetOwningContainer(this, &v14);
  Container::GetContainerSetupTask(v14, &v16);
  v2 = v16;
  v3 = (*(__int64 (__fastcall **)(_QWORD, RTL_SRWLOCK *, _QWORD, _QWORD))(**((_QWORD **)this + 16) + 24LL))(
         *((_QWORD *)this + 16),
         v16,
         *((_QWORD *)this + 12),
         *((unsigned int *)this + 22));
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x412,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
      (const char *)(unsigned int)v3,
      v13);
LABEL_3:
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    return v4;
  }
  v6 = lambda_5bb2a98cf85b373dd723daae1fbe55f9_::_lambda_5bb2a98cf85b373dd723daae1fbe55f9_(&v22, this);
  wil::scope_exit__lambda_5bb2a98cf85b373dd723daae1fbe55f9___(v18, v6);
  v7 = (const OLECHAR *)((char *)this + 40);
  if ( *((_QWORD *)this + 8) <= 7u )
    v8 = (char *)this + 40;
  else
    v8 = *(char **)v7;
  v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 16) + 40LL))(*((_QWORD *)this + 16), v8);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( *(_BYTE *)(v14 + 40) )
    {
      *(_OWORD *)pvar = 0;
      v20 = 0;
      if ( *((_QWORD *)this + 8) > 7u )
        v7 = *(const OLECHAR **)v7;
      DevnodeList = CDsmDeviceScan::GetDevnodeList(v7, pvar);
      v4 = DevnodeList;
      if ( DevnodeList < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x422,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
          (const char *)(unsigned int)DevnodeList,
          v13);
        PropVariantClear(pvar);
        wil::details::lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___::_lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___(v18);
        goto LABEL_3;
      }
      for ( i = 0; (unsigned int)i < LODWORD(pvar[1]); i = (unsigned int)(i + 1) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF__guid_LS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            (unsigned int)&WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids,
            (_DWORD)this + 8,
            *((_DWORD *)this + 7),
            *(_QWORD *)(v20 + 8 * i));
        }
        if ( (int)CDsmPropertyCache::SetDevnodeObject(
                    (CDsmPropertyCache *)&v2[13],
                    *(const unsigned __int16 **)(v20 + 8 * i)) >= 0 )
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 16) + 56LL))(
            *((_QWORD *)this + 16),
            *(_QWORD *)(v20 + 8 * i));
          CDsmPropertyCache::CommitCachedDevnodeProperties(v2 + 13);
        }
      }
      PropVariantClear(pvar);
    }
    wil::details::lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___::_lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___(v18);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x419,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
      (const char *)(unsigned int)v9,
      v13);
    wil::details::lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___::_lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___(v18);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    return v10;
  }
}

```

## disassembly

```asm
0x180012a48  push    rbp
0x180012a4a  push    rbx
0x180012a4b  push    rsi
0x180012a4c  push    rdi
0x180012a4d  push    r14
0x180012a4f  push    r15
0x180012a51  lea     rbp, [rsp-2Fh]
0x180012a56  sub     rsp, 88h
0x180012a5d  mov     rdi, rcx
0x180012a60  lea     rdx, [rbp+57h+var_80]
0x180012a64  call    ?GetOwningContainer@Job@@QEAA?AV?$shared_ptr@VContainer@@@std@@XZ; Job::GetOwningContainer(void)
0x180012a69  nop
0x180012a6a  lea     rdx, [rbp+57h+var_70]
0x180012a6e  mov     rcx, [rbp+57h+var_80]
0x180012a72  call    ?GetContainerSetupTask@Container@@QEAA?AV?$shared_ptr@VCDsmTask@@@std@@XZ; Container::GetContainerSetupTask(void)
0x180012a77  nop
0x180012a78  mov     rcx, [rdi+80h]
0x180012a7f  mov     rax, [rcx]
0x180012a82  mov     r9d, [rdi+58h]
0x180012a86  mov     r8, [rdi+60h]
0x180012a8a  mov     r15, [rbp+57h+var_70]
0x180012a8e  mov     rdx, r15
0x180012a91  mov     rax, [rax+18h]
0x180012a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a9a  mov     ebx, eax
0x180012a9c  test    eax, eax
0x180012a9e  jns     short loc_180012ADD
0x180012aa0  mov     rcx, [rbp+5Fh]; this
0x180012aa4  mov     r9d, eax; char *
0x180012aa7  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180012aae  mov     edx, 412h; void *
0x180012ab3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ab8  nop
0x180012ab9  mov     rcx, [rbp+57h+var_68]; this
0x180012abd  test    rcx, rcx
0x180012ac0  jz      short loc_180012AC8
0x180012ac2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012ac7  nop
0x180012ac8  mov     rcx, [rbp+57h+var_78]; this
0x180012acc  test    rcx, rcx
0x180012acf  jz      short loc_180012AD6
0x180012ad1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012ad6  mov     eax, ebx
0x180012ad8  jmp     loc_180012CA4
0x180012add  mov     rdx, rdi
0x180012ae0  lea     rcx, [rbp+57h+arg_0]
0x180012ae4  call    _lambda_5bb2a98cf85b373dd723daae1fbe55f9____lambda_5bb2a98cf85b373dd723daae1fbe55f9_
0x180012ae9  mov     rdx, rax
0x180012aec  lea     rcx, [rbp+57h+var_60]
0x180012af0  call    wil__scope_exit__lambda_5bb2a98cf85b373dd723daae1fbe55f9___
0x180012af5  nop
0x180012af6  mov     rcx, [rdi+80h]
0x180012afd  mov     rax, [rcx]
0x180012b00  lea     rbx, [rdi+28h]
0x180012b04  cmp     qword ptr [rbx+18h], 7
0x180012b09  jbe     short loc_180012B10
0x180012b0b  mov     rdx, [rbx]
0x180012b0e  jmp     short loc_180012B13
0x180012b10  mov     rdx, rbx
0x180012b13  mov     rax, [rax+28h]
0x180012b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b1c  mov     esi, eax
0x180012b1e  test    eax, eax
0x180012b20  jns     short loc_180012B69
0x180012b22  mov     rcx, [rbp+5Fh]; this
0x180012b26  mov     r9d, eax; char *
0x180012b29  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180012b30  mov     edx, 419h; void *
0x180012b35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b3a  nop
0x180012b3b  lea     rcx, [rbp+57h+var_60]
0x180012b3f  call    wil__details__lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9______lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___
0x180012b44  nop
0x180012b45  mov     rcx, [rbp+57h+var_68]; this
0x180012b49  test    rcx, rcx
0x180012b4c  jz      short loc_180012B54
0x180012b4e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012b53  nop
0x180012b54  mov     rcx, [rbp+57h+var_78]; this
0x180012b58  test    rcx, rcx
0x180012b5b  jz      short loc_180012B62
0x180012b5d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012b62  mov     eax, esi
0x180012b64  jmp     loc_180012CA4
0x180012b69  mov     rax, [rbp+57h+var_80]
0x180012b6d  cmp     byte ptr [rax+28h], 0
0x180012b71  jz      loc_180012C7B
0x180012b77  xorps   xmm0, xmm0
0x180012b7a  xor     eax, eax
0x180012b7c  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180012b80  mov     [rbp+57h+var_40], rax
0x180012b84  cmp     qword ptr [rbx+18h], 7
0x180012b89  jbe     short loc_180012B8E
0x180012b8b  mov     rbx, [rbx]
0x180012b8e  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180012b92  mov     rcx, rbx; lpsz
0x180012b95  call    ?GetDevnodeList@CDsmDeviceScan@@SAJPEBGPEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::GetDevnodeList(ushort const *,tagPROPVARIANT *)
0x180012b9a  mov     ebx, eax
0x180012b9c  test    eax, eax
0x180012b9e  jns     short loc_180012BD2
0x180012ba0  mov     rcx, [rbp+5Fh]; this
0x180012ba4  mov     r9d, eax; char *
0x180012ba7  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180012bae  mov     edx, 422h; void *
0x180012bb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012bb8  nop
0x180012bb9  lea     rcx, [rbp+57h+pvar]; pvar
0x180012bbd  call    cs:__imp_PropVariantClear
0x180012bc3  nop
0x180012bc4  lea     rcx, [rbp+57h+var_60]
0x180012bc8  call    wil__details__lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9______lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___
0x180012bcd  jmp     loc_180012AB9
0x180012bd2  xor     ebx, ebx
0x180012bd4  cmp     dword ptr [rbp+57h+pvar+8], ebx
0x180012bd7  jbe     loc_180012C70
0x180012bdd  lea     rax, WPP_GLOBAL_Control
0x180012be4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012beb  cmp     rcx, rax
0x180012bee  jz      short loc_180012C2C
0x180012bf0  test    dword ptr [rcx+1Ch], 200h
0x180012bf7  jz      short loc_180012C2C
0x180012bf9  cmp     byte ptr [rcx+19h], 4
0x180012bfd  jb      short loc_180012C2C
0x180012bff  lea     r9, [rdi+8]
0x180012c03  mov     edx, 2Ch ; ','
0x180012c08  mov     rax, [rbp+57h+var_40]
0x180012c0c  mov     r8, [rax+rbx*8]
0x180012c10  mov     [rsp+0B0h+var_88], r8
0x180012c15  mov     eax, [rdi+1Ch]
0x180012c18  mov     [rsp+0B0h+var_90], eax
0x180012c1c  lea     r8, WPP_ae76cb39094131aa87b75fea7a3ef403_Traceguids
0x180012c23  mov     rcx, [rcx+10h]
0x180012c27  call    WPP_SF__guid_LS
0x180012c2c  mov     rdx, [rbp+57h+var_40]
0x180012c30  mov     rdx, [rdx+rbx*8]; unsigned __int16 *
0x180012c34  lea     rcx, [r15+68h]; this
0x180012c38  call    ?SetDevnodeObject@CDsmPropertyCache@@QEAAJPEBG@Z; CDsmPropertyCache::SetDevnodeObject(ushort const *)
0x180012c3d  test    eax, eax
0x180012c3f  js      short loc_180012C65
0x180012c41  mov     rcx, [rdi+80h]
0x180012c48  mov     rax, [rcx]
0x180012c4b  mov     rdx, [rbp+57h+var_40]
0x180012c4f  mov     rdx, [rdx+rbx*8]
0x180012c53  mov     rax, [rax+38h]
0x180012c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c5c  lea     rcx, [r15+68h]; this
0x180012c60  call    ?CommitCachedDevnodeProperties@CDsmPropertyCache@@QEAAXXZ; CDsmPropertyCache::CommitCachedDevnodeProperties(void)
0x180012c65  inc     ebx
0x180012c67  cmp     ebx, dword ptr [rbp+57h+pvar+8]
0x180012c6a  jb      loc_180012BDD
0x180012c70  lea     rcx, [rbp+57h+pvar]; pvar
0x180012c74  call    cs:__imp_PropVariantClear
0x180012c7a  nop
0x180012c7b  lea     rcx, [rbp+57h+var_60]
0x180012c7f  call    wil__details__lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9______lambda_call__lambda_5bb2a98cf85b373dd723daae1fbe55f9___
0x180012c84  nop
0x180012c85  mov     rcx, [rbp+57h+var_68]; this
0x180012c89  test    rcx, rcx
0x180012c8c  jz      short loc_180012C94
0x180012c8e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012c93  nop
0x180012c94  mov     rcx, [rbp+57h+var_78]; this
0x180012c98  test    rcx, rcx
0x180012c9b  jz      short loc_180012CA2
0x180012c9d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012ca2  xor     eax, eax
0x180012ca4  add     rsp, 88h
0x180012cab  pop     r15
0x180012cad  pop     r14
0x180012caf  pop     rdi
0x180012cb0  pop     rsi
0x180012cb1  pop     rbx
0x180012cb2  pop     rbp
0x180012cb3  retn
```
