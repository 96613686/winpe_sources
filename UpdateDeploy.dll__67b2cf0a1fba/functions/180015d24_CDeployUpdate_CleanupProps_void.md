# CDeployUpdate::CleanupProps(void)

- ea: `0x180015d24`
- end: `0x180015e05`
- name: `?CleanupProps@CDeployUpdate@@QEAAXXZ`
- size: `225`
- prototype: `void __fastcall(CDeployUpdate *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180015b94`
- `0x180023fdc`

## callees

- `0x18000dc1c`
- `0x18000dce4`
- `0x180015d24`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015dbf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015d71`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015dac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180015dbf`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall CDeployUpdate::CleanupProps(CDeployUpdate *this)
{
  void *v1; // rsi
  unsigned int v3; // eax
  LPVOID *v4; // rdi
  __int64 v5; // rbp
  void *v6; // rsi
  unsigned int v7; // eax
  LPVOID *v8; // rdi
  __int64 v9; // rbp
  void *v10; // rcx

  v1 = (void *)*((_QWORD *)this + 60);
  if ( v1 )
  {
    v3 = *((_DWORD *)this + 118);
    if ( v3 )
    {
      v4 = (LPVOID *)*((_QWORD *)this + 60);
      v5 = v3;
      do
      {
        if ( *v4 )
          CoTaskMemFree(*v4);
        ++v4;
        --v5;
      }
      while ( v5 );
      CoTaskMemFree(v1);
    }
  }
  SusFreePtrArray(*((void **)this + 62), *((unsigned int *)this + 123));
  v6 = (void *)*((_QWORD *)this + 66);
  if ( v6 )
  {
    v7 = *((_DWORD *)this + 131);
    if ( v7 )
    {
      v8 = (LPVOID *)*((_QWORD *)this + 66);
      v9 = v7;
      do
      {
        if ( *v8 )
          CoTaskMemFree(*v8);
        ++v8;
        --v9;
      }
      while ( v9 );
      CoTaskMemFree(v6);
    }
  }
  *(GUID *)((char *)this + 504) = GUID_NULL;
  v10 = (void *)*((_QWORD *)this + 71);
  if ( v10 )
    SusFree(v10);
  *((_QWORD *)this + 71) = 0;
}

```

## disassembly

```asm
0x180015d24  mov     [rsp+arg_0], rbx
0x180015d29  mov     [rsp+arg_8], rbp
0x180015d2e  mov     [rsp+arg_10], rsi
0x180015d33  push    rdi
0x180015d34  sub     rsp, 20h
0x180015d38  mov     rsi, [rcx+1E0h]
0x180015d3f  mov     rbx, rcx
0x180015d42  test    rsi, rsi
0x180015d45  jz      short loc_180015D77
0x180015d47  mov     eax, [rcx+1D8h]
0x180015d4d  test    eax, eax
0x180015d4f  jz      short loc_180015D77
0x180015d51  mov     rdi, rsi
0x180015d54  mov     ebp, eax
0x180015d56  mov     rcx, [rdi]; pv
0x180015d59  test    rcx, rcx
0x180015d5c  jz      short loc_180015D64
0x180015d5e  call    cs:__imp_CoTaskMemFree
0x180015d64  add     rdi, 8
0x180015d68  sub     rbp, 1
0x180015d6c  jnz     short loc_180015D56
0x180015d6e  mov     rcx, rsi; pv
0x180015d71  call    cs:__imp_CoTaskMemFree
0x180015d77  mov     edx, [rbx+1ECh]; unsigned __int64
0x180015d7d  mov     rcx, [rbx+1F0h]; lpMem
0x180015d84  call    ?SusFreePtrArray@@YAXPEAX_K@Z; SusFreePtrArray(void *,unsigned __int64)
0x180015d89  mov     rsi, [rbx+210h]
0x180015d90  test    rsi, rsi
0x180015d93  jz      short loc_180015DC5
0x180015d95  mov     eax, [rbx+20Ch]
0x180015d9b  test    eax, eax
0x180015d9d  jz      short loc_180015DC5
0x180015d9f  mov     rdi, rsi
0x180015da2  mov     ebp, eax
0x180015da4  mov     rcx, [rdi]; pv
0x180015da7  test    rcx, rcx
0x180015daa  jz      short loc_180015DB2
0x180015dac  call    cs:__imp_CoTaskMemFree
0x180015db2  add     rdi, 8
0x180015db6  sub     rbp, 1
0x180015dba  jnz     short loc_180015DA4
0x180015dbc  mov     rcx, rsi; pv
0x180015dbf  call    cs:__imp_CoTaskMemFree
0x180015dc5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180015dcc  movdqu  xmmword ptr [rbx+1F8h], xmm0
0x180015dd4  mov     rcx, [rbx+238h]; lpMem
0x180015ddb  test    rcx, rcx
0x180015dde  jz      short loc_180015DE5
0x180015de0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180015de5  mov     rbp, [rsp+28h+arg_8]
0x180015dea  mov     rsi, [rsp+28h+arg_10]
0x180015def  mov     qword ptr [rbx+238h], 0
0x180015dfa  mov     rbx, [rsp+28h+arg_0]
0x180015dff  add     rsp, 20h
0x180015e03  pop     rdi
0x180015e04  retn
```
