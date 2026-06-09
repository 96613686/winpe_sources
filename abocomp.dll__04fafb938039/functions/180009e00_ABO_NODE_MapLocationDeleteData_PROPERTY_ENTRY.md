# ABO_NODE::MapLocationDeleteData(PROPERTY_ENTRY *)

- ea: `0x180009e00`
- end: `0x180009fbe`
- name: `?MapLocationDeleteData@ABO_NODE@@AEAAJPEAVPROPERTY_ENTRY@@@Z`
- size: `446`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, struct PROPERTY_ENTRY *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180009b84`

## callees

- `0x18000341a`
- `0x180003460`
- `0x180003f14`
- `0x180007a80`
- `0x180009e00`
- `0x18001775c`
- `0x18002c010`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180009ee5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180009ee5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009e84`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180009e84`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009e5f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009e5f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009f8c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009f8c`

## pseudocode

```c
__int64 __fastcall ABO_NODE::MapLocationDeleteData(ABO_NODE *this, struct PROPERTY_ENTRY *a2)
{
  int v4; // ebx
  struct PROPERTY_ID_TABLE *v5; // rbx
  unsigned int *Ptr; // rax
  int Key; // eax
  HANDLE_ENTRY *v8; // rsi
  int v9; // r12d
  unsigned int v10; // r14d
  __int64 *v11; // rdi
  __int64 v12; // rax
  __int64 (__fastcall *v13)(__int64 *, const unsigned __int16 *, struct INativeConfigurationElement **); // rbx
  const unsigned __int16 *Str; // rax
  int v15; // eax
  struct INativeConfigurationElement *v17; // [rsp+20h] [rbp-E0h] BYREF
  HANDLE_ENTRY *v18; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v19[64]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v20[256]; // [rsp+70h] [rbp-90h] BYREF

  v18 = 0;
  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v19, v20, 0x100u);
  v17 = 0;
  if ( a2 )
  {
    v5 = g_pPropertyIdTable;
    Ptr = (unsigned int *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
    Key = CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,unsigned long,CLKRHashTable>::FindKey((char *)v5 + 8, *Ptr, &v18);
    v8 = v18;
    if ( Key )
      goto LABEL_13;
    if ( !*((_QWORD *)this + 29) )
      goto LABEL_13;
    v9 = 0;
    v10 = 0;
    if ( !*((_DWORD *)v18 + 22) )
      goto LABEL_13;
    do
    {
      v11 = (__int64 *)*((_QWORD *)this + 29);
      v12 = *v11;
      v18 = *(HANDLE_ENTRY **)(*((_QWORD *)v8 + 10) + 8LL * v10);
      v13 = *(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, struct INativeConfigurationElement **))(v12 + 72);
      Str = STRU::QueryStr((HANDLE_ENTRY *)((char *)v18 + 32));
      v15 = v13(v11, Str, &v17);
      v4 = v15;
      if ( v15 >= 0 )
      {
        v4 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v18, this, v17);
        if ( v4 < 0 )
          goto LABEL_14;
        v9 = 1;
        (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
        v17 = 0;
      }
      else
      {
        if ( v15 != -2147024894 )
          goto LABEL_14;
        v4 = 0;
      }
      ++v10;
    }
    while ( v10 < *((_DWORD *)v8 + 22) );
    if ( !v9 )
LABEL_13:
      v4 = -2147024894;
LABEL_14:
    if ( v8 )
      HANDLE_ENTRY::DereferenceHandleEntry(v8);
    if ( v17 )
    {
      (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v17 + 16LL))(v17);
      v17 = 0;
    }
  }
  else
  {
    v4 = -2147024809;
  }
  STRU::~STRU((STRU *)v19);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009e00  mov     [rsp-8+arg_10], rbx
0x180009e05  push    rbp
0x180009e06  push    rsi
0x180009e07  push    rdi
0x180009e08  push    r12
0x180009e0a  push    r13
0x180009e0c  push    r14
0x180009e0e  push    r15
0x180009e10  lea     rbp, [rsp-180h]
0x180009e18  sub     rsp, 280h
0x180009e1f  mov     rax, cs:__security_cookie
0x180009e26  xor     rax, rsp
0x180009e29  mov     [rbp+1B0h+var_40], rax
0x180009e30  mov     r15, rdx
0x180009e33  mov     r13, rcx
0x180009e36  xor     edi, edi
0x180009e38  lea     rcx, [rsp+2B0h+var_240]; void *
0x180009e3d  xor     edx, edx; Val
0x180009e3f  mov     [rsp+2B0h+var_288], rdi
0x180009e44  mov     r8d, 200h; Size
0x180009e4a  call    memset_0
0x180009e4f  mov     r8d, 100h
0x180009e55  lea     rdx, [rsp+2B0h+var_240]
0x180009e5a  lea     rcx, [rsp+2B0h+var_280]
0x180009e5f  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009e65  mov     [rsp+2B0h+var_290], rdi
0x180009e6a  test    r15, r15
0x180009e6d  jnz     short loc_180009E79
0x180009e6f  mov     ebx, 80070057h
0x180009e74  jmp     loc_180009F87
0x180009e79  mov     rbx, cs:?g_pPropertyIdTable@@3PEAVPROPERTY_ID_TABLE@@EA; PROPERTY_ID_TABLE * g_pPropertyIdTable
0x180009e80  lea     rcx, [r15+10h]
0x180009e84  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180009e8a  lea     r8, [rsp+2B0h+var_288]
0x180009e8f  lea     rcx, [rbx+8]
0x180009e93  mov     edx, [rax]
0x180009e95  call    ?FindKey@?$CTypedHashTable@VHANDLE_TABLE@@VHANDLE_ENTRY@@KVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@KPEAPEAVHANDLE_ENTRY@@@Z; CTypedHashTable<HANDLE_TABLE,HANDLE_ENTRY,ulong,CLKRHashTable>::FindKey(ulong,HANDLE_ENTRY * *)
0x180009e9a  mov     rsi, [rsp+2B0h+var_288]
0x180009e9f  test    eax, eax
0x180009ea1  jnz     loc_180009F5A
0x180009ea7  cmp     [r13+0E8h], rdi
0x180009eae  jz      loc_180009F5A
0x180009eb4  mov     r12d, edi
0x180009eb7  mov     r14d, edi
0x180009eba  cmp     [rsi+58h], edi
0x180009ebd  jbe     loc_180009F5A
0x180009ec3  mov     rax, [rsi+50h]
0x180009ec7  mov     rdi, [r13+0E8h]
0x180009ece  mov     ecx, r14d
0x180009ed1  mov     rcx, [rax+rcx*8]
0x180009ed5  mov     rax, [rdi]
0x180009ed8  mov     [rsp+2B0h+var_288], rcx
0x180009edd  add     rcx, 20h ; ' '
0x180009ee1  mov     rbx, [rax+48h]
0x180009ee5  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180009eeb  lea     r8, [rsp+2B0h+var_290]
0x180009ef0  mov     rcx, rdi
0x180009ef3  mov     rdx, rax
0x180009ef6  mov     rax, rbx
0x180009ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009efe  xor     edi, edi
0x180009f00  mov     ebx, eax
0x180009f02  test    eax, eax
0x180009f04  jns     short loc_180009F11
0x180009f06  cmp     eax, 80070002h
0x180009f0b  jnz     short loc_180009F5F
0x180009f0d  mov     ebx, edi
0x180009f0f  jmp     short loc_180009F48
0x180009f11  mov     r9, [rsp+2B0h+var_290]; struct INativeConfigurationElement *
0x180009f16  mov     r8, r13; struct ABO_NODE *
0x180009f19  mov     rdx, [rsp+2B0h+var_288]; struct PROPERTY_MAPPING *
0x180009f1e  mov     rcx, r15; struct PROPERTY_ENTRY *
0x180009f21  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x180009f26  mov     ebx, eax
0x180009f28  test    eax, eax
0x180009f2a  js      short loc_180009F5F
0x180009f2c  mov     rcx, [rsp+2B0h+var_290]
0x180009f31  mov     r12d, 1
0x180009f37  mov     rax, [rcx]
0x180009f3a  mov     rax, [rax+10h]
0x180009f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f43  mov     [rsp+2B0h+var_290], rdi
0x180009f48  inc     r14d
0x180009f4b  cmp     r14d, [rsi+58h]
0x180009f4f  jb      loc_180009EC3
0x180009f55  test    r12d, r12d
0x180009f58  jnz     short loc_180009F5F
0x180009f5a  mov     ebx, 80070002h
0x180009f5f  test    rsi, rsi
0x180009f62  jz      short loc_180009F6C
0x180009f64  mov     rcx, rsi; this
0x180009f67  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180009f6c  mov     rcx, [rsp+2B0h+var_290]
0x180009f71  test    rcx, rcx
0x180009f74  jz      short loc_180009F87
0x180009f76  mov     rax, [rcx]
0x180009f79  mov     rax, [rax+10h]
0x180009f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f82  mov     [rsp+2B0h+var_290], rdi
0x180009f87  lea     rcx, [rsp+2B0h+var_280]
0x180009f8c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180009f92  mov     eax, ebx
0x180009f94  mov     rcx, [rbp+1B0h+var_40]
0x180009f9b  xor     rcx, rsp; StackCookie
0x180009f9e  call    __security_check_cookie
0x180009fa3  mov     rbx, [rsp+2B0h+arg_10]
0x180009fab  add     rsp, 280h
0x180009fb2  pop     r15
0x180009fb4  pop     r14
0x180009fb6  pop     r13
0x180009fb8  pop     r12
0x180009fba  pop     rdi
0x180009fbb  pop     rsi
0x180009fbc  pop     rbp
0x180009fbd  retn
```
