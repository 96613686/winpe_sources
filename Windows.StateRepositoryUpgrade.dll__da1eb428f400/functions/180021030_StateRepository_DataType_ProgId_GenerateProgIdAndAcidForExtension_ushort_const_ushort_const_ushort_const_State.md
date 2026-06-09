# StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)

- ea: `0x180021030`
- end: `0x18002128c`
- name: `?GenerateProgIdAndAcidForExtension@ProgId@DataType@StateRepository@@YAJPEBG00W4RuntimeBehavior@3@W4SRTrustLevel@3@00000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@3@Z`
- size: `604`
- prototype: `__int64 __fastcall(_WORD *, _WORD *, const unsigned __int16 *, int, int, unsigned __int16 *, __int64, _WORD *, __int64, __int64, __int64, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x18000d9c4`
- `0x18000dc30`
- `0x18000de98`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000a77c`
- `0x180014ca0`
- `0x180020714`
- `0x180020780`
- `0x180020c20`
- `0x180021030`
- `0x180021294`

## string_xrefs

- `0x18002105d`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`
- `0x180021235`: `onecore\base\appmodel\staterepository\dataaccesslayer\datatype-progid.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DataType::ProgId::GenerateProgIdAndAcidForExtension(
        _WORD *a1,
        _WORD *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        unsigned __int16 *a6,
        __int64 a7,
        _WORD *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        unsigned __int16 **a12)
{
  const unsigned __int16 *v12; // rbx
  __int64 v14; // rdx
  int ProgIdForExtension; // ebx
  _WORD *v17; // rdi
  __int64 v18; // rax
  unsigned __int64 v19; // rbp
  __int64 unique; // rax
  unsigned __int16 **v21; // r14
  void *v22; // rcx
  int v23; // eax
  int v24; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  void *Block; // [rsp+A0h] [rbp+8h] BYREF

  v12 = a3;
  if ( !a1 )
  {
    v14 = 364;
LABEL_3:
    ProgIdForExtension = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
      (const char *)(unsigned int)ProgIdForExtension,
      v24);
    return (unsigned int)ProgIdForExtension;
  }
  if ( !*a1 )
  {
    v14 = 365;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v14 = 366;
    goto LABEL_3;
  }
  if ( !*a2 )
  {
    v14 = 367;
    goto LABEL_3;
  }
  v17 = a8;
  if ( !a8 )
  {
    v14 = 368;
    goto LABEL_3;
  }
  if ( !*a8 )
  {
    v14 = 369;
    goto LABEL_3;
  }
  if ( a7 )
  {
    ProgIdForExtension = StateRepository::DataType::ProgId::GenerateProgIdForExtension(
                           (_DWORD)a1,
                           (unsigned int)L".wwa",
                           (_DWORD)a2,
                           (_DWORD)a3,
                           a4,
                           a5,
                           (__int64)a8,
                           a9,
                           a7,
                           a11,
                           (__int64)a12);
    if ( ProgIdForExtension < 0 )
    {
      v14 = 377;
      goto LABEL_4;
    }
  }
  else if ( (unsigned int)(a4 - 2) <= 2 )
  {
    if ( !a3 )
      v12 = a6;
    v18 = -1;
    do
      ++v18;
    while ( v12[v18] );
    v19 = v18 + 1;
    unique = wil::make_unique_nothrow<unsigned short [0]>(&Block, v18 + 1);
    v21 = a12;
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(a12, unique);
    v22 = Block;
    Block = 0;
    if ( v22 )
      operator delete(v22);
    if ( !*v21 )
    {
      ProgIdForExtension = -2147024882;
      v14 = 389;
      goto LABEL_4;
    }
    v23 = StringCchCopyW(*v21, v19, v12);
    if ( v23 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\datatype-progid.cpp",
        (const char *)(unsigned int)v23,
        v24);
    v24 = a11;
    ProgIdForExtension = StateRepository::DataType::ProgId::GenerateProgId(a1, v12, v17, a9);
    if ( ProgIdForExtension < 0 )
    {
      v14 = 391;
      goto LABEL_4;
    }
  }
  else
  {
    ProgIdForExtension = StateRepository::DataType::ProgId::GenerateProgIdForExtension(
                           (_DWORD)a1,
                           (unsigned int)L".mca",
                           (_DWORD)a2,
                           (_DWORD)a3,
                           a4,
                           a5,
                           (__int64)a8,
                           a9,
                           a10,
                           a11,
                           (__int64)a12);
    if ( ProgIdForExtension < 0 )
    {
      v14 = 399;
      goto LABEL_4;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180021030  push    rbx
0x180021032  push    rbp
0x180021033  push    rsi
0x180021034  push    rdi
0x180021035  push    r14
0x180021037  push    r15
0x180021039  sub     rsp, 68h
0x18002103d  xor     r15d, r15d
0x180021040  mov     rbx, r8
0x180021043  mov     rsi, rcx
0x180021046  test    rcx, rcx
0x180021049  jnz     short loc_180021073
0x18002104b  mov     edx, 16Ch; void *
0x180021050  mov     ebx, 80070057h
0x180021055  mov     rcx, [rsp+98h]; this
0x18002105d  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x180021064  mov     r9d, ebx; char *
0x180021067  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002106c  mov     eax, ebx
0x18002106e  jmp     loc_18002127F
0x180021073  cmp     [rcx], r15w
0x180021077  jnz     short loc_180021080
0x180021079  mov     edx, 16Dh
0x18002107e  jmp     short loc_180021050
0x180021080  test    rdx, rdx
0x180021083  jnz     short loc_18002108C
0x180021085  mov     edx, 16Eh
0x18002108a  jmp     short loc_180021050
0x18002108c  cmp     [rdx], r15w
0x180021090  jnz     short loc_180021099
0x180021092  mov     edx, 16Fh
0x180021097  jmp     short loc_180021050
0x180021099  mov     rdi, [rsp+98h+arg_38]
0x1800210a1  test    rdi, rdi
0x1800210a4  jnz     short loc_1800210AD
0x1800210a6  mov     edx, 170h
0x1800210ab  jmp     short loc_180021050
0x1800210ad  cmp     [rdi], r15w
0x1800210b1  jnz     short loc_1800210BA
0x1800210b3  mov     edx, 171h
0x1800210b8  jmp     short loc_180021050
0x1800210ba  mov     rcx, [rsp+98h+arg_30]
0x1800210c2  test    rcx, rcx
0x1800210c5  jz      short loc_180021131
0x1800210c7  mov     rax, [rsp+98h+arg_58]
0x1800210cf  mov     r8, rdx
0x1800210d2  mov     [rsp+98h+var_48], rax
0x1800210d7  lea     rdx, aWwa; ".wwa"
0x1800210de  mov     rax, [rsp+98h+arg_50]
0x1800210e6  mov     [rsp+98h+var_50], rax
0x1800210eb  mov     rax, [rsp+98h+arg_40]
0x1800210f3  mov     [rsp+98h+var_58], rcx
0x1800210f8  mov     rcx, rsi
0x1800210fb  mov     [rsp+98h+var_60], rax
0x180021100  mov     eax, [rsp+98h+arg_20]
0x180021107  mov     [rsp+98h+var_68], rdi
0x18002110c  mov     [rsp+98h+var_70], eax
0x180021110  mov     dword ptr [rsp+98h+var_78], r9d
0x180021115  mov     r9, rbx
0x180021118  call    ?GenerateProgIdForExtension@ProgId@DataType@StateRepository@@YAJPEBG000W4RuntimeBehavior@3@W4SRTrustLevel@3@000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@3@Z; StateRepository::DataType::ProgId::GenerateProgIdForExtension(ushort const *,ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18002111d  mov     ebx, eax
0x18002111f  test    eax, eax
0x180021121  jns     loc_18002127D
0x180021127  mov     edx, 179h
0x18002112c  jmp     loc_180021055
0x180021131  lea     eax, [r9-2]
0x180021135  cmp     eax, 2
0x180021138  jbe     short loc_1800211AC
0x18002113a  mov     rax, [rsp+98h+arg_58]
0x180021142  mov     r8, rdx
0x180021145  mov     [rsp+98h+var_48], rax
0x18002114a  lea     rdx, aMca; ".mca"
0x180021151  mov     rax, [rsp+98h+arg_50]
0x180021159  mov     rcx, rsi
0x18002115c  mov     [rsp+98h+var_50], rax
0x180021161  mov     rax, [rsp+98h+arg_48]
0x180021169  mov     [rsp+98h+var_58], rax
0x18002116e  mov     rax, [rsp+98h+arg_40]
0x180021176  mov     [rsp+98h+var_60], rax
0x18002117b  mov     eax, [rsp+98h+arg_20]
0x180021182  mov     [rsp+98h+var_68], rdi
0x180021187  mov     [rsp+98h+var_70], eax
0x18002118b  mov     dword ptr [rsp+98h+var_78], r9d
0x180021190  mov     r9, rbx
0x180021193  call    ?GenerateProgIdForExtension@ProgId@DataType@StateRepository@@YAJPEBG000W4RuntimeBehavior@3@W4SRTrustLevel@3@000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@3@Z; StateRepository::DataType::ProgId::GenerateProgIdForExtension(ushort const *,ushort const *,ushort const *,ushort const *,StateRepository::RuntimeBehavior,StateRepository::SRTrustLevel,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x180021198  mov     ebx, eax
0x18002119a  test    eax, eax
0x18002119c  jns     loc_18002127D
0x1800211a2  mov     edx, 18Fh
0x1800211a7  jmp     loc_180021055
0x1800211ac  test    rbx, rbx
0x1800211af  cmovz   rbx, [rsp+98h+arg_28]
0x1800211b8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800211bc  inc     rax
0x1800211bf  cmp     [rbx+rax*2], r15w
0x1800211c4  jnz     short loc_1800211BC
0x1800211c6  lea     rbp, [rax+1]
0x1800211ca  mov     rdx, rbp
0x1800211cd  lea     rcx, [rsp+98h+Block]
0x1800211d5  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800211da  mov     r14, [rsp+98h+arg_58]
0x1800211e2  mov     rdx, rax
0x1800211e5  mov     rcx, r14
0x1800211e8  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800211ed  mov     rcx, [rsp+98h+Block]; Block
0x1800211f5  mov     [rsp+98h+Block], r15
0x1800211fd  test    rcx, rcx
0x180021200  jz      short loc_180021207
0x180021202  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021207  mov     rcx, [r14]; unsigned __int16 *
0x18002120a  test    rcx, rcx
0x18002120d  jnz     short loc_18002121E
0x18002120f  mov     ebx, 8007000Eh
0x180021214  mov     edx, 185h
0x180021219  jmp     loc_180021055
0x18002121e  mov     r8, rbx; unsigned __int16 *
0x180021221  mov     rdx, rbp; unsigned __int64
0x180021224  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180021229  test    eax, eax
0x18002122b  jns     short loc_18002124A
0x18002122d  mov     rcx, [rsp+98h]; this
0x180021235  lea     r8, aOnecoreBaseApp_23; "onecore\\base\\appmodel\\staterepositor"...
0x18002123c  mov     r9d, eax; char *
0x18002123f  mov     edx, 186h; void *
0x180021244  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002124a  mov     rax, [rsp+98h+arg_50]
0x180021252  mov     r8, rdi
0x180021255  mov     r9, [rsp+98h+arg_40]
0x18002125d  mov     rdx, rbx
0x180021260  mov     rcx, rsi
0x180021263  mov     [rsp+98h+var_78], rax
0x180021268  call    ?GenerateProgId@ProgId@DataType@StateRepository@@YAJPEBG000AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; StateRepository::DataType::ProgId::GenerateProgId(ushort const *,ushort const *,ushort const *,ushort const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18002126d  mov     ebx, eax
0x18002126f  test    eax, eax
0x180021271  jns     short loc_18002127D
0x180021273  mov     edx, 187h
0x180021278  jmp     loc_180021055
0x18002127d  xor     eax, eax
0x18002127f  add     rsp, 68h
0x180021283  pop     r15
0x180021285  pop     r14
0x180021287  pop     rdi
0x180021288  pop     rsi
0x180021289  pop     rbp
0x18002128a  pop     rbx
0x18002128b  retn
```
