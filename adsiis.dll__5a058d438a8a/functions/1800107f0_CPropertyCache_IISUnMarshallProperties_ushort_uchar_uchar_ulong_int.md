# CPropertyCache::IISUnMarshallProperties(ushort *,uchar *,uchar *,ulong,int)

- ea: `0x1800107f0`
- end: `0x180010961`
- name: `?IISUnMarshallProperties@CPropertyCache@@QEAAJPEAGPEAE1KH@Z`
- size: `369`
- prototype: `__int64 __usercall@<rax>(CPropertyCache *__hidden this@<rcx>, unsigned __int16 *@<rdx>, unsigned __int8 *@<r8>, unsigned __int8 *@<r9>, unsigned int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006090`

## callees

- `0x1800107f0`
- `0x180010968`
- `0x1800110bc`
- `0x18001a290`
- `0x18001b524`
- `0x18001bc84`
- `0x18001d66a`
- `0x18001d6c0`

## pseudocode

```c
__int64 __fastcall CPropertyCache::IISUnMarshallProperties(
        IIsSchema **this,
        unsigned __int16 *a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        unsigned int a5,
        int a6)
{
  int Schema; // ecx
  unsigned int v11; // r9d
  unsigned int v12; // edi
  IIsSchema *v13; // rcx
  __int64 v14; // rbx
  unsigned __int8 *v15; // rax
  unsigned int i; // r9d
  unsigned int v18[4]; // [rsp+30h] [rbp-278h] BYREF
  unsigned __int16 v19[264]; // [rsp+40h] [rbp-268h] BYREF

  v18[0] = 0;
  memset_0(v19, 0, 0x208u);
  Schema = CPropertyCache::LoadSchema((CPropertyCache *)this);
  if ( Schema >= 0 )
  {
    v12 = 0;
    *((_DWORD *)this + 10) = 1;
    while ( v12 < a5 )
    {
      v13 = this[9];
      v14 = 28LL * v12;
      v19[0] = 0;
      if ( IIsSchema::IdToPropNameW(v13, *(_DWORD *)&a4[v14], v19, v11) < 0
        || (int)IIsSchema::LookupSyntaxID(this[9], v19, v18) < 0
        || IIsSchema::ValidateProperty(this[9], a2, v19) < 0 )
      {
        Schema = 0;
      }
      else
      {
        if ( *(_DWORD *)&a4[v14 + 12] == 5 )
        {
          v15 = &a3[*(unsigned int *)&a4[v14 + 20]];
          for ( i = *(_WORD *)v15 == 0; *(_WORD *)v15; ++i )
          {
            do
              v15 += 2;
            while ( *(_WORD *)v15 );
            v15 += 2;
          }
        }
        else if ( *(_DWORD *)&a4[v14 + 12] == 3 )
        {
          i = *(_DWORD *)&a4[v14 + 16];
        }
        else
        {
          i = 1;
        }
        Schema = CPropertyCache::unmarshallproperty(
                   (CPropertyCache *)this,
                   v19,
                   &a3[*(unsigned int *)&a4[v14 + 20]],
                   i,
                   v18[0],
                   a6);
        if ( Schema < 0 )
          Schema = 0;
      }
      ++v12;
    }
  }
  return (unsigned int)Schema;
}

```

## disassembly

```asm
0x1800107f0  push    rbx
0x1800107f2  push    rbp
0x1800107f3  push    rsi
0x1800107f4  push    rdi
0x1800107f5  push    r12
0x1800107f7  push    r13
0x1800107f9  push    r14
0x1800107fb  push    r15
0x1800107fd  sub     rsp, 268h
0x180010804  mov     rax, cs:__security_cookie
0x18001080b  xor     rax, rsp
0x18001080e  mov     [rsp+2A8h+var_58], rax
0x180010816  mov     r14, r8
0x180010819  mov     r12, rdx
0x18001081c  mov     rsi, rcx
0x18001081f  xor     r13d, r13d
0x180010822  xor     edx, edx; Val
0x180010824  mov     [rsp+2A8h+var_278], r13d
0x180010829  mov     r8d, 208h; Size
0x18001082f  lea     rcx, [rsp+2A8h+var_268]; void *
0x180010834  mov     rbp, r9
0x180010837  call    memset_0
0x18001083c  mov     rcx, rsi; this
0x18001083f  call    ?LoadSchema@CPropertyCache@@IEAAJXZ; CPropertyCache::LoadSchema(void)
0x180010844  mov     ecx, eax
0x180010846  test    eax, eax
0x180010848  js      loc_18001093B
0x18001084e  mov     r15d, [rsp+2A8h+arg_28]
0x180010856  mov     edi, r13d
0x180010859  mov     dword ptr [rsi+28h], 1
0x180010860  cmp     edi, [rsp+2A8h+arg_20]
0x180010867  jnb     loc_18001093B
0x18001086d  mov     rcx, [rsi+48h]; this
0x180010871  lea     r8, [rsp+2A8h+var_268]; unsigned __int16 *
0x180010876  mov     eax, edi
0x180010878  imul    rbx, rax, 1Ch
0x18001087c  mov     [rsp+2A8h+var_268], r13w
0x180010882  mov     edx, [rbx+rbp]; unsigned int
0x180010885  call    ?IdToPropNameW@IIsSchema@@QEAAJKPEAGK@Z; IIsSchema::IdToPropNameW(ulong,ushort *,ulong)
0x18001088a  test    eax, eax
0x18001088c  jns     short loc_180010896
0x18001088e  mov     ecx, r13d
0x180010891  jmp     loc_180010934
0x180010896  mov     rcx, [rsi+48h]; this
0x18001089a  lea     r8, [rsp+2A8h+var_278]; unsigned int *
0x18001089f  lea     rdx, [rsp+2A8h+var_268]; unsigned __int16 *
0x1800108a4  call    ?LookupSyntaxID@IIsSchema@@QEAAJPEBGPEAK@Z; IIsSchema::LookupSyntaxID(ushort const *,ulong *)
0x1800108a9  test    eax, eax
0x1800108ab  js      short loc_18001088E
0x1800108ad  mov     rcx, [rsi+48h]; this
0x1800108b1  lea     r8, [rsp+2A8h+var_268]; unsigned __int16 *
0x1800108b6  mov     rdx, r12; unsigned __int16 *
0x1800108b9  call    ?ValidateProperty@IIsSchema@@QEAAJPEBG0@Z; IIsSchema::ValidateProperty(ushort const *,ushort const *)
0x1800108be  test    eax, eax
0x1800108c0  js      short loc_18001088E
0x1800108c2  cmp     dword ptr [rbx+rbp+0Ch], 5
0x1800108c7  jnz     short loc_1800108F6
0x1800108c9  mov     eax, [rbx+rbp+14h]
0x1800108cd  mov     r9d, r13d
0x1800108d0  add     rax, r14
0x1800108d3  cmp     [rax], r13w
0x1800108d7  setz    r9b
0x1800108db  jz      short loc_18001090A
0x1800108dd  add     rax, 2
0x1800108e1  cmp     [rax], r13w
0x1800108e5  jnz     short loc_1800108DD
0x1800108e7  add     rax, 2
0x1800108eb  inc     r9d
0x1800108ee  cmp     [rax], r13w
0x1800108f2  jnz     short loc_1800108DD
0x1800108f4  jmp     short loc_18001090A
0x1800108f6  cmp     dword ptr [rbx+rbp+0Ch], 3
0x1800108fb  jnz     short loc_180010904
0x1800108fd  mov     r9d, [rbx+rbp+10h]
0x180010902  jmp     short loc_18001090A
0x180010904  mov     r9d, 1; unsigned int
0x18001090a  mov     r8d, [rbx+rbp+14h]
0x18001090f  lea     rdx, [rsp+2A8h+var_268]; unsigned __int16 *
0x180010914  mov     eax, [rsp+2A8h+var_278]
0x180010918  add     r8, r14; unsigned __int8 *
0x18001091b  mov     [rsp+2A8h+var_280], r15d; int
0x180010920  mov     rcx, rsi; this
0x180010923  mov     [rsp+2A8h+var_288], eax; unsigned int
0x180010927  call    ?unmarshallproperty@CPropertyCache@@QEAAJPEAGPEAEKKH@Z; CPropertyCache::unmarshallproperty(ushort *,uchar *,ulong,ulong,int)
0x18001092c  test    eax, eax
0x18001092e  mov     ecx, eax
0x180010930  cmovs   ecx, r13d
0x180010934  inc     edi
0x180010936  jmp     loc_180010860
0x18001093b  mov     eax, ecx
0x18001093d  mov     rcx, [rsp+2A8h+var_58]
0x180010945  xor     rcx, rsp; StackCookie
0x180010948  call    __security_check_cookie
0x18001094d  add     rsp, 268h
0x180010954  pop     r15
0x180010956  pop     r14
0x180010958  pop     r13
0x18001095a  pop     r12
0x18001095c  pop     rdi
0x18001095d  pop     rsi
0x18001095e  pop     rbp
0x18001095f  pop     rbx
0x180010960  retn
```
