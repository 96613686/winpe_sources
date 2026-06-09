# CConnectorProcessingModeCharacteristics::AddConnectorFormat(tWAVEFORMATEX const *,uint,uint,uint,uint,uint)

- ea: `0x18001b7b4`
- end: `0x18001b943`
- name: `?AddConnectorFormat@CConnectorProcessingModeCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@IIIII@Z`
- size: `399`
- prototype: `__int64 __fastcall(CConnectorProcessingModeCharacteristics *this, const struct tWAVEFORMATEX *, int, int, unsigned int, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800197e4`
- `0x180019ce8`
- `0x18001a8d0`

## callees

- `0x180010da8`
- `0x18001b778`
- `0x18001b7b4`
- `0x180036f80`
- `0x18003edc0`
- `0x18003edfc`
- `0x18005d794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b91b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b886`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b8b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b91b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnectorProcessingModeCharacteristics::AddConnectorFormat(
        CConnectorProcessingModeCharacteristics *this,
        const struct tWAVEFORMATEX *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  void **v10; // rax
  void **v11; // rbx
  __int64 result; // rax
  int v13; // edi
  void *v14; // rcx
  void *v15; // rcx
  const char *v16; // r9
  void *v17; // rbx
  void *v18; // rcx
  void *v19; // [rsp+20h] [rbp-58h] BYREF
  void **v20; // [rsp+28h] [rbp-50h]
  struct tWAVEFORMATEX *v21; // [rsp+30h] [rbp-48h] BYREF
  char v22; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v10 = (void **)operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    v10[1] = 0;
    v10[2] = 0;
    v10[3] = 0;
    *v10 = 0;
  }
  else
  {
    v11 = 0;
  }
  v19 = v11;
  if ( v11 )
  {
    v20 = v11;
    v21 = 0;
    v22 = 1;
    v13 = CloneWaveFormat(a2, &v21);
    if ( v22 )
    {
      v14 = *v20;
      *v20 = v21;
      if ( v14 )
        CoTaskMemFree(v14);
    }
    if ( v13 >= 0 )
    {
      *((_DWORD *)v11 + 3) = a3;
      *((_DWORD *)v11 + 2) = a4;
      *((_DWORD *)v11 + 4) = a5;
      *((_DWORD *)v11 + 5) = a6;
      *((_DWORD *)v11 + 6) = a7;
      try
      {
        std::vector<std::unique_ptr<CConnectorFormatCharacteristics>>::emplace_back<std::unique_ptr<CConnectorFormatCharacteristics>>();
        v17 = v19;
        if ( v19 )
        {
          v18 = *(void **)v19;
          *(_QWORD *)v19 = 0;
          if ( v18 )
            CoTaskMemFree(v18);
          operator delete(v17, 0x20u);
        }
        result = 0;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0xF7,
                               (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
                               v16);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEC,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
        (const char *)(unsigned int)v13,
        (int)v19);
      v15 = *v11;
      *v11 = 0;
      if ( v15 )
        CoTaskMemFree(v15);
      operator delete(v11, 0x20u);
      return (unsigned int)v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEA,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioengineutil\\endpointutil.cpp",
      (const char *)0x8007000ELL,
      0);
    std::unique_ptr<CConnectorFormatCharacteristics>::~unique_ptr<CConnectorFormatCharacteristics>(&v19);
    return 2147942414LL;
  }
  return result;
}

```

## disassembly

```asm
0x18001b7b4  push    rbx
0x18001b7b6  push    rsi
0x18001b7b7  push    rdi
0x18001b7b8  push    r13
0x18001b7ba  push    r14
0x18001b7bc  push    r15
0x18001b7be  sub     rsp, 48h
0x18001b7c2  mov     esi, r9d
0x18001b7c5  mov     r14d, r8d
0x18001b7c8  mov     rdi, rdx
0x18001b7cb  mov     r15, rcx
0x18001b7ce  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b7d5  mov     r13d, 20h ; ' '
0x18001b7db  mov     ecx, r13d; unsigned __int64
0x18001b7de  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b7e3  mov     rbx, rax
0x18001b7e6  test    rax, rax
0x18001b7e9  jz      short loc_18001B80C
0x18001b7eb  mov     qword ptr [rax+8], 0
0x18001b7f3  mov     qword ptr [rax+10h], 0
0x18001b7fb  mov     qword ptr [rax+18h], 0
0x18001b803  mov     qword ptr [rax], 0
0x18001b80a  jmp     short loc_18001B80E
0x18001b80c  xor     ebx, ebx
0x18001b80e  mov     [rsp+78h+var_58], rbx; int
0x18001b813  test    rbx, rbx
0x18001b816  jnz     short loc_18001B848
0x18001b818  mov     rcx, [rsp+78h]; this
0x18001b81d  mov     ebx, 8007000Eh
0x18001b822  mov     r9d, ebx; char *
0x18001b825  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001b82c  mov     edx, 0EAh; void *
0x18001b831  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b836  nop
0x18001b837  lea     rcx, [rsp+78h+var_58]
0x18001b83c  call    ??1?$unique_ptr@UCConnectorFormatCharacteristics@@U?$default_delete@UCConnectorFormatCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorFormatCharacteristics>::~unique_ptr<CConnectorFormatCharacteristics>(void)
0x18001b841  mov     eax, ebx
0x18001b843  jmp     loc_18001B934
0x18001b848  mov     [rsp+78h+var_50], rbx
0x18001b84d  mov     [rsp+78h+var_48], 0
0x18001b856  mov     [rsp+78h+var_40], 1
0x18001b85b  lea     rdx, [rsp+78h+var_48]; struct tWAVEFORMATEX **
0x18001b860  mov     rcx, rdi; Src
0x18001b863  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x18001b868  mov     edi, eax
0x18001b86a  cmp     [rsp+78h+var_40], 0
0x18001b86f  jz      short loc_18001B88C
0x18001b871  mov     r8, [rsp+78h+var_50]
0x18001b876  mov     rcx, [r8]; pv
0x18001b879  mov     rdx, [rsp+78h+var_48]
0x18001b87e  mov     [r8], rdx
0x18001b881  test    rcx, rcx
0x18001b884  jz      short loc_18001B88C
0x18001b886  call    cs:__imp_CoTaskMemFree
0x18001b88c  test    edi, edi
0x18001b88e  jns     short loc_18001B8CE
0x18001b890  mov     rcx, [rsp+78h]; this
0x18001b895  mov     r9d, edi; char *
0x18001b898  lea     r8, aAvcoreAudiocor_15; "avcore\\audiocore\\server\\lib\\audioen"...
0x18001b89f  mov     edx, 0ECh; void *
0x18001b8a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b8a9  nop
0x18001b8aa  mov     rcx, [rbx]; pv
0x18001b8ad  mov     qword ptr [rbx], 0
0x18001b8b4  test    rcx, rcx
0x18001b8b7  jz      short loc_18001B8BF
0x18001b8b9  call    cs:__imp_CoTaskMemFree
0x18001b8bf  mov     rdx, r13; unsigned __int64
0x18001b8c2  mov     rcx, rbx; void *
0x18001b8c5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b8ca  mov     eax, edi
0x18001b8cc  jmp     short loc_18001B934
0x18001b8ce  mov     [rbx+0Ch], r14d
0x18001b8d2  mov     [rbx+8], esi
0x18001b8d5  mov     eax, [rsp+78h+arg_20]
0x18001b8dc  mov     [rbx+10h], eax
0x18001b8df  mov     eax, [rsp+78h+arg_28]
0x18001b8e6  mov     [rbx+14h], eax
0x18001b8e9  mov     eax, [rsp+78h+arg_30]
0x18001b8f0  mov     [rbx+18h], eax
0x18001b8f3  lea     rcx, [r15+10h]
0x18001b8f7  lea     rdx, [rsp+78h+var_58]
0x18001b8fc  call    ??$emplace_back@V?$unique_ptr@UCConnectorFormatCharacteristics@@U?$default_delete@UCConnectorFormatCharacteristics@@@std@@@std@@@?$vector@V?$unique_ptr@UCConnectorFormatCharacteristics@@U?$default_delete@UCConnectorFormatCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@UCConnectorFormatCharacteristics@@U?$default_delete@UCConnectorFormatCharacteristics@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@UCConnectorFormatCharacteristics@@U?$default_delete@UCConnectorFormatCharacteristics@@@std@@@1@$$QEAV21@@Z; std::vector<std::unique_ptr<CConnectorFormatCharacteristics>>::emplace_back<std::unique_ptr<CConnectorFormatCharacteristics>>(std::unique_ptr<CConnectorFormatCharacteristics> &&)
0x18001b901  nop
0x18001b902  mov     rbx, [rsp+78h+var_58]
0x18001b907  test    rbx, rbx
0x18001b90a  jz      short loc_18001B92C
0x18001b90c  mov     rcx, [rbx]; pv
0x18001b90f  mov     qword ptr [rbx], 0
0x18001b916  test    rcx, rcx
0x18001b919  jz      short loc_18001B921
0x18001b91b  call    cs:__imp_CoTaskMemFree
0x18001b921  mov     rdx, r13; unsigned __int64
0x18001b924  mov     rcx, rbx; void *
0x18001b927  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b92c  xor     eax, eax
0x18001b92e  jmp     short loc_18001B934
0x18001b930  mov     eax, dword ptr [rsp+78h+var_58]
0x18001b934  add     rsp, 48h
0x18001b938  pop     r15
0x18001b93a  pop     r14
0x18001b93c  pop     r13
0x18001b93e  pop     rdi
0x18001b93f  pop     rsi
0x18001b940  pop     rbx
0x18001b941  retn
```
