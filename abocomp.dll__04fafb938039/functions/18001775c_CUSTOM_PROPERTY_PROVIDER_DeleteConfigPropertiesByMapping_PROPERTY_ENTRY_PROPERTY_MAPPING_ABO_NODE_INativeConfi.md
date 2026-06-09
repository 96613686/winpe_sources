# CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x18001775c`
- end: `0x1800179c7`
- name: `?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `619`
- prototype: `static int(struct PROPERTY_ENTRY *, struct PROPERTY_MAPPING *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `13`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180009e00`
- `0x180012310`
- `0x180013290`
- `0x180015500`
- `0x1800179d0`
- `0x180019680`
- `0x18001a130`
- `0x18001aaf0`
- `0x18001b630`
- `0x18001ba70`
- `0x180026160`
- `0x180026710`
- `0x18002b560`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18001775c`
- `0x180017c24`
- `0x18002c010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180017828`
- `msvcrt!wcsrchr` at `0x180017828`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001788e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18001788e`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001781a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017839`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001784b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017880`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001781a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017839`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001784b`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017880`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800177c3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800177e9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800177c3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800177e9`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017991`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001799c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017991`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001799c`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180017877`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x180017877`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800178c8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017950`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800178c8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180017950`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800178a3`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001791c`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x1800178a3`
- `iisutil!?IsEmpty@STRU@@QEBA_NXZ` at `0x18001791c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001785c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18001785c`

## pseudocode

```c
__int64 __fastcall CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(
        struct PROPERTY_ENTRY *a1,
        struct PROPERTY_MAPPING *a2,
        struct ABO_NODE *a3,
        struct INativeConfigurationElement *a4)
{
  const wchar_t *Str; // rax
  wchar_t *v9; // r15
  __int64 v10; // rbx
  const unsigned __int16 *v11; // rax
  int v12; // ebx
  const unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // rax
  __int64 v15; // rcx
  int v16; // eax
  __int64 (__fastcall *v17)(struct INativeConfigurationElement *, unsigned __int16 *); // rbx
  unsigned __int16 *v18; // rax
  struct INativeConfigurationElement *v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[56]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v22[64]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v23[256]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v24[256]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v20 = 0;
  memset_0(v23, 0, sizeof(v23));
  STRU::STRU((STRU *)v22, v23, 0x100u);
  memset_0(v24, 0, sizeof(v24));
  STRU::STRU((STRU *)v21, v24, 0x100u);
  if ( a1 && a4 && a2 && a3 )
  {
    Str = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 88));
    v9 = wcsrchr(Str, 0x2Eu);
    if ( v9 )
    {
      v10 = v9 - STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 88));
      v11 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 88));
      v12 = STRU::Copy((STRU *)v21, v11, v10);
      if ( v12 < 0 )
        goto LABEL_20;
      v13 = v9 + 1;
    }
    else
    {
      STRU::Reset((STRU *)v21);
      v13 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)a2 + 88));
    }
    v12 = STRU::Copy((STRU *)v22, v13);
    if ( v12 >= 0 )
    {
      if ( STRU::IsEmpty((STRU *)v21) )
      {
        v20 = a4;
        (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)a4 + 8LL))(a4);
LABEL_13:
        v15 = *((_QWORD *)a2 + 22);
        if ( v15 )
        {
          v16 = (*(__int64 (__fastcall **)(__int64, struct PROPERTY_MAPPING *, struct PROPERTY_ENTRY *, struct ABO_NODE *, struct INativeConfigurationElement *))(*(_QWORD *)v15 + 24LL))(
                  v15,
                  a2,
                  a1,
                  a3,
                  v20);
        }
        else if ( STRU::IsEmpty((STRU *)v22) )
        {
          v16 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 168LL))(v20);
        }
        else
        {
          v17 = *(__int64 (__fastcall **)(struct INativeConfigurationElement *, unsigned __int16 *))(*(_QWORD *)v20 + 184LL);
          v18 = STRU::QueryStr((STRU *)v22);
          v16 = v17(v20, v18);
        }
        v12 = v16;
        goto LABEL_20;
      }
      v14 = STRU::QueryStr((STRU *)v21);
      v12 = CUSTOM_PROPERTY_PROVIDER::OpenElement(v14, a4, &v20);
      if ( v12 >= 0 )
        goto LABEL_13;
    }
  }
  else
  {
    v12 = -2147024809;
  }
LABEL_20:
  if ( v20 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v20 + 16LL))(v20);
    v20 = 0;
  }
  STRU::~STRU((STRU *)v21);
  STRU::~STRU((STRU *)v22);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18001775c  push    rbp
0x18001775e  push    rbx
0x18001775f  push    rsi
0x180017760  push    rdi
0x180017761  push    r12
0x180017763  push    r13
0x180017765  push    r14
0x180017767  push    r15
0x180017769  lea     rbp, [rsp-3C8h]
0x180017771  sub     rsp, 4C8h
0x180017778  mov     rax, cs:__security_cookie
0x18001777f  xor     rax, rsp
0x180017782  mov     [rbp+400h+var_50], rax
0x180017789  mov     r12, r8
0x18001778c  mov     [rsp+500h+var_4D0], 0
0x180017795  mov     rsi, rdx
0x180017798  mov     r13, rcx
0x18001779b  mov     r14d, 200h
0x1800177a1  lea     rcx, [rbp+400h+var_450]; void *
0x1800177a5  mov     r8d, r14d; Size
0x1800177a8  xor     edx, edx; Val
0x1800177aa  mov     rdi, r9
0x1800177ad  call    memset_0
0x1800177b2  mov     ebx, 100h
0x1800177b7  lea     rdx, [rbp+400h+var_450]
0x1800177bb  mov     r8d, ebx
0x1800177be  lea     rcx, [rsp+500h+var_490]
0x1800177c3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800177c9  mov     r8d, r14d; Size
0x1800177cc  lea     rcx, [rbp+400h+var_250]; void *
0x1800177d3  xor     edx, edx; Val
0x1800177d5  call    memset_0
0x1800177da  mov     r8d, ebx
0x1800177dd  lea     rdx, [rbp+400h+var_250]
0x1800177e4  lea     rcx, [rsp+500h+var_4C8]
0x1800177e9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800177ef  test    r13, r13
0x1800177f2  jz      loc_180017968
0x1800177f8  test    rdi, rdi
0x1800177fb  jz      loc_180017968
0x180017801  test    rsi, rsi
0x180017804  jz      loc_180017968
0x18001780a  test    r12, r12
0x18001780d  jz      loc_180017968
0x180017813  lea     r14, [rsi+58h]
0x180017817  mov     rcx, r14
0x18001781a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180017820  mov     rcx, rax; Str
0x180017823  mov     edx, 2Eh ; '.'; Ch
0x180017828  call    cs:__imp_wcsrchr
0x18001782e  mov     r15, rax
0x180017831  test    rax, rax
0x180017834  jz      short loc_180017872
0x180017836  mov     rcx, r14
0x180017839  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001783f  mov     rbx, r15
0x180017842  mov     rcx, r14
0x180017845  sub     rbx, rax
0x180017848  sar     rbx, 1
0x18001784b  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180017851  mov     r8d, ebx
0x180017854  lea     rcx, [rsp+500h+var_4C8]
0x180017859  mov     rdx, rax
0x18001785c  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180017862  mov     ebx, eax
0x180017864  test    eax, eax
0x180017866  js      loc_18001796D
0x18001786c  lea     rdx, [r15+2]
0x180017870  jmp     short loc_180017889
0x180017872  lea     rcx, [rsp+500h+var_4C8]
0x180017877  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x18001787d  mov     rcx, r14
0x180017880  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180017886  mov     rdx, rax
0x180017889  lea     rcx, [rsp+500h+var_490]
0x18001788e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017894  mov     ebx, eax
0x180017896  test    eax, eax
0x180017898  js      loc_18001796D
0x18001789e  lea     rcx, [rsp+500h+var_4C8]
0x1800178a3  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x1800178a9  test    al, al
0x1800178ab  jz      short loc_1800178C3
0x1800178ad  mov     [rsp+500h+var_4D0], rdi
0x1800178b2  mov     rcx, rdi
0x1800178b5  mov     rax, [rdi]
0x1800178b8  mov     rax, [rax+8]
0x1800178bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178c1  jmp     short loc_1800178E8
0x1800178c3  lea     rcx, [rsp+500h+var_4C8]
0x1800178c8  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800178ce  lea     r8, [rsp+500h+var_4D0]; struct INativeConfigurationElement **
0x1800178d3  mov     rdx, rdi; struct INativeConfigurationElement *
0x1800178d6  mov     rcx, rax; unsigned __int16 *
0x1800178d9  call    ?OpenElement@CUSTOM_PROPERTY_PROVIDER@@CAJPEBGPEAVINativeConfigurationElement@@PEAPEAV2@@Z; CUSTOM_PROPERTY_PROVIDER::OpenElement(ushort const *,INativeConfigurationElement *,INativeConfigurationElement * *)
0x1800178de  mov     ebx, eax
0x1800178e0  test    eax, eax
0x1800178e2  js      loc_18001796D
0x1800178e8  mov     rcx, [rsi+0B0h]
0x1800178ef  test    rcx, rcx
0x1800178f2  jz      short loc_180017917
0x1800178f4  mov     rax, [rcx]
0x1800178f7  mov     r9, r12
0x1800178fa  mov     r10, [rsp+500h+var_4D0]
0x1800178ff  mov     r8, r13
0x180017902  mov     rdx, rsi
0x180017905  mov     [rsp+500h+var_4E0], r10
0x18001790a  mov     rax, [rax+18h]
0x18001790e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017913  mov     ebx, eax
0x180017915  jmp     short loc_18001796D
0x180017917  lea     rcx, [rsp+500h+var_490]
0x18001791c  call    cs:__imp_?IsEmpty@STRU@@QEBA_NXZ; STRU::IsEmpty(void)
0x180017922  test    al, al
0x180017924  jz      short loc_18001793C
0x180017926  mov     rcx, [rsp+500h+var_4D0]
0x18001792b  mov     rax, [rcx]
0x18001792e  mov     rax, [rax+0A8h]
0x180017935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001793a  jmp     short loc_180017913
0x18001793c  mov     rax, [rsp+500h+var_4D0]
0x180017941  mov     rcx, [rax]
0x180017944  mov     rbx, [rcx+0B8h]
0x18001794b  lea     rcx, [rsp+500h+var_490]
0x180017950  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180017956  mov     rcx, [rsp+500h+var_4D0]
0x18001795b  mov     rdx, rax
0x18001795e  mov     rax, rbx
0x180017961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017966  jmp     short loc_180017913
0x180017968  mov     ebx, 80070057h
0x18001796d  mov     rcx, [rsp+500h+var_4D0]
0x180017972  test    rcx, rcx
0x180017975  jz      short loc_18001798C
0x180017977  mov     rax, [rcx]
0x18001797a  mov     rax, [rax+10h]
0x18001797e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017983  mov     [rsp+500h+var_4D0], 0
0x18001798c  lea     rcx, [rsp+500h+var_4C8]
0x180017991  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017997  lea     rcx, [rsp+500h+var_490]
0x18001799c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800179a2  mov     eax, ebx
0x1800179a4  mov     rcx, [rbp+400h+var_50]
0x1800179ab  xor     rcx, rsp; StackCookie
0x1800179ae  call    __security_check_cookie
0x1800179b3  add     rsp, 4C8h
0x1800179ba  pop     r15
0x1800179bc  pop     r14
0x1800179be  pop     r13
0x1800179c0  pop     r12
0x1800179c2  pop     rdi
0x1800179c3  pop     rsi
0x1800179c4  pop     rbx
0x1800179c5  pop     rbp
0x1800179c6  retn
```
