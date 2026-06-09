# CNamespaceManagement::CreateClassAssociationsToDriver(ushort *,uchar *,ulong,ulong)

- ea: `0x1800178d8`
- end: `0x180017a24`
- name: `?CreateClassAssociationsToDriver@CNamespaceManagement@@QEAAJPEAGPEAEKK@Z`
- size: `332`
- prototype: `__int64 __fastcall(CNamespaceManagement *__hidden this, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000226c`
- `0x180002a5c`

## callees

- `0x180003e10`
- `0x1800178d8`
- `0x180017a2c`
- `0x180017cb0`
- `0x180019c94`
- `0x180019eb0`
- `0x180019f6c`

## import_xrefs

- `msvcrt!free` at `0x1800179c8`
- `msvcrt!free` at `0x1800179d1`
- `msvcrt!free` at `0x1800179df`
- `msvcrt!free` at `0x180017a0b`
- `msvcrt!free` at `0x1800179c8`
- `msvcrt!free` at `0x1800179d1`
- `msvcrt!free` at `0x1800179df`
- `msvcrt!free` at `0x180017a0b`
- `msvcrt!malloc` at `0x180017922`
- `msvcrt!malloc` at `0x180017922`
- `wbemcomn!ErrorTrace` at `0x1800179f3`
- `wbemcomn!ErrorTrace` at `0x1800179f3`

## pseudocode

```c
__int64 __fastcall CNamespaceManagement::CreateClassAssociationsToDriver(
        CNamespaceManagement *this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned int a4,
        unsigned int a5)
{
  int v8; // eax
  char *v9; // rdi
  unsigned int v10; // ebp
  _QWORD *v11; // rax
  _DWORD *v12; // rbx
  __int64 v13; // rcx
  unsigned int v14; // r15d
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 Obj; // rax
  void *v18; // rsi
  void *Block; // [rsp+80h] [rbp+8h] BYREF

  Block = 0;
  v8 = CWMIBinMof::DecompressBinaryMof(this, a3, (unsigned __int8 **)&Block);
  v9 = (char *)Block;
  v10 = v8;
  if ( v8 < 0 )
  {
    ErrorTrace(10, "Could not tie classes to driver for file:\n");
    TranslateAndLog(a2, 0);
  }
  else
  {
    v11 = malloc(0x20u);
    v12 = v11;
    if ( v11 )
    {
      *v11 = v9;
      v11[2] = v9 + 20;
      ResetObjList(v11);
      ResetObjList(v13);
      v14 = a5;
      while ( 1 )
      {
        v15 = v12[2];
        v16 = *(_DWORD *)(*(_QWORD *)v12 + 16LL);
        v12[2] = v15 + 1;
        if ( v15 >= v16 )
          break;
        Obj = CreateObj(*((_QWORD *)v12 + 3));
        v18 = (void *)Obj;
        *((_QWORD *)v12 + 3) += **((unsigned int **)v12 + 3);
        if ( !Obj )
          break;
        Block = 0;
        if ( (unsigned int)GetName(Obj, &Block) )
        {
          CNamespaceManagement::CreateInstance(this, a2, (unsigned __int16 *)Block, a4, v14);
          free(Block);
        }
        free(v18);
      }
      free(v12);
    }
  }
  if ( v9 )
    free(v9);
  return v10;
}

```

## disassembly

```asm
0x1800178d8  mov     r11, rsp
0x1800178db  push    rbx
0x1800178dc  push    rbp
0x1800178dd  push    rsi
0x1800178de  push    rdi
0x1800178df  push    r12
0x1800178e1  push    r13
0x1800178e3  push    r14
0x1800178e5  push    r15
0x1800178e7  sub     rsp, 38h
0x1800178eb  mov     rax, r8
0x1800178ee  mov     qword ptr [r11+8], 0
0x1800178f6  mov     r14, rdx
0x1800178f9  lea     r8, [r11+8]; unsigned __int8 **
0x1800178fd  mov     rdx, rax; unsigned __int8 *
0x180017900  mov     r12d, r9d
0x180017903  mov     r13, rcx
0x180017906  call    ?DecompressBinaryMof@CWMIBinMof@@QEAAJPEAEPEAPEAE@Z; CWMIBinMof::DecompressBinaryMof(uchar *,uchar * *)
0x18001790b  mov     rdi, [rsp+78h+Block]
0x180017913  mov     ebp, eax
0x180017915  test    eax, eax
0x180017917  js      loc_1800179E7
0x18001791d  mov     ecx, 20h ; ' '; Size
0x180017922  call    cs:__imp_malloc
0x180017928  mov     rbx, rax
0x18001792b  test    rax, rax
0x18001792e  jz      loc_180017A03
0x180017934  lea     rcx, [rdi+14h]
0x180017938  mov     [rax], rdi
0x18001793b  mov     [rax+10h], rcx
0x18001793f  mov     rcx, rax
0x180017942  call    ResetObjList
0x180017947  call    ResetObjList
0x18001794c  mov     r15d, [rsp+78h+arg_20]
0x180017954  mov     edx, [rbx+8]
0x180017957  mov     rax, [rbx]
0x18001795a  mov     ecx, [rax+10h]
0x18001795d  lea     eax, [rdx+1]
0x180017960  mov     [rbx+8], eax
0x180017963  cmp     edx, ecx
0x180017965  jnb     short loc_1800179DC
0x180017967  mov     rcx, [rbx+18h]
0x18001796b  call    CreateObj
0x180017970  mov     rcx, [rbx+18h]
0x180017974  mov     rsi, rax
0x180017977  mov     edx, [rcx]
0x180017979  add     rdx, rcx
0x18001797c  mov     [rbx+18h], rdx
0x180017980  test    rax, rax
0x180017983  jz      short loc_1800179DC
0x180017985  lea     rdx, [rsp+78h+Block]
0x18001798d  mov     [rsp+78h+Block], 0
0x180017999  mov     rcx, rax
0x18001799c  call    GetName
0x1800179a1  test    eax, eax
0x1800179a3  jz      short loc_1800179CE
0x1800179a5  mov     r8, [rsp+78h+Block]; unsigned __int16 *
0x1800179ad  mov     r9d, r12d; unsigned int
0x1800179b0  mov     rdx, r14; unsigned __int16 *
0x1800179b3  mov     [rsp+78h+var_58], r15d; unsigned int
0x1800179b8  mov     rcx, r13; this
0x1800179bb  call    ?CreateInstance@CNamespaceManagement@@QEAAHPEAG0KK@Z; CNamespaceManagement::CreateInstance(ushort *,ushort *,ulong,ulong)
0x1800179c0  mov     rcx, [rsp+78h+Block]; Block
0x1800179c8  call    cs:__imp_free
0x1800179ce  mov     rcx, rsi; Block
0x1800179d1  call    cs:__imp_free
0x1800179d7  jmp     loc_180017954
0x1800179dc  mov     rcx, rbx; Block
0x1800179df  call    cs:__imp_free
0x1800179e5  jmp     short loc_180017A03
0x1800179e7  lea     rdx, aCouldNotTieCla; "Could not tie classes to driver for fil"...
0x1800179ee  mov     ecx, 0Ah
0x1800179f3  call    cs:__imp_?ErrorTrace@@YAHDPEBDZZ; ErrorTrace(char,char const *,...)
0x1800179f9  xor     edx, edx; int
0x1800179fb  mov     rcx, r14; lpWideCharStr
0x1800179fe  call    ?TranslateAndLog@@YAXPEAGH@Z; TranslateAndLog(ushort *,int)
0x180017a03  test    rdi, rdi
0x180017a06  jz      short loc_180017A11
0x180017a08  mov     rcx, rdi; Block
0x180017a0b  call    cs:__imp_free
0x180017a11  mov     eax, ebp
0x180017a13  add     rsp, 38h
0x180017a17  pop     r15
0x180017a19  pop     r14
0x180017a1b  pop     r13
0x180017a1d  pop     r12
0x180017a1f  pop     rdi
0x180017a20  pop     rsi
0x180017a21  pop     rbp
0x180017a22  pop     rbx
0x180017a23  retn
```
