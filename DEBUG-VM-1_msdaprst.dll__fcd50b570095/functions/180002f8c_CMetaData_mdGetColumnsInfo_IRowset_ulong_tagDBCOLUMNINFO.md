# CMetaData::mdGetColumnsInfo(IRowset *,ulong,tagDBCOLUMNINFO *)

- ea: `0x180002f8c`
- end: `0x1800030bb`
- name: `?mdGetColumnsInfo@CMetaData@@AEAAXPEAUIRowset@@KPEAUtagDBCOLUMNINFO@@@Z`
- size: `303`
- prototype: `void __fastcall(CMetaData *__hidden this, struct IRowset *, unsigned int, struct tagDBCOLUMNINFO *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180002b1c`

## callees

- `0x180002ec0`
- `0x180002f8c`
- `0x18001a6c8`
- `0x18002cd54`
- `0x18002e02a`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180002fb7`
- `ole32!CoTaskMemAlloc` at `0x180002fb7`

## pseudocode

```c
void __fastcall CMetaData::mdGetColumnsInfo(
        CMetaData *this,
        struct IRowset *a2,
        unsigned int a3,
        struct tagDBCOLUMNINFO *a4)
{
  SIZE_T v6; // rbx
  unsigned __int16 v7; // si
  void *v9; // rax
  unsigned __int16 v10; // r15
  unsigned __int16 v11; // bx
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  union tagDBID::$8A6F84EEDBA9444E5F3B3798E7B3D46D uGuid; // xmm1
  __int128 v15; // xmm0
  int ColInfo; // eax
  unsigned __int16 v17; // cx
  struct tagDBCOLUMNINFO v18; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int16 v19; // [rsp+D0h] [rbp+18h] BYREF

  v6 = 168LL * a3;
  v7 = 0;
  v19 = 0;
  v9 = CoTaskMemAlloc(v6);
  *((_QWORD *)this + 1) = v9;
  if ( !v9 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180048448[0] )
        bidTraceW(off_1800481B8[0], 540672, off_180048448[0], 2147942414LL, 528);
    }
    ThrowHR(-2147024882);
  }
  memset_0(v9, 0, v6);
  v10 = 0;
  v11 = 0;
  if ( a3 )
  {
    do
    {
      v12 = *(_OWORD *)&a4[v10].iOrdinal;
      *(_OWORD *)&v18.pwszName = *(_OWORD *)&a4[v10].pwszName;
      v13 = *(_OWORD *)&a4[v10].ulColumnSize;
      *(_OWORD *)&v18.iOrdinal = v12;
      uGuid = a4[v10].columnid.uGuid;
      *(_OWORD *)&v18.ulColumnSize = v13;
      v15 = *(_OWORD *)&a4[v10].columnid.eKind;
      v18.columnid.uGuid = uGuid;
      *(_OWORD *)&v18.columnid.eKind = v15;
      ColInfo = CMetaData::mdGetColInfo(this, &v18, v11, &v19);
      v17 = v11 + 1;
      if ( !ColInfo )
        v17 = v11;
      ++v10;
      v11 = v17;
    }
    while ( v10 < a3 );
    v7 = v19;
  }
  *(_WORD *)this = v11;
  *((_WORD *)this + 1) = v11 - v7;
  *((_WORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180002f8c  mov     rax, rsp
0x180002f8f  push    rbx
0x180002f90  push    rbp
0x180002f91  push    rsi
0x180002f92  push    rdi
0x180002f93  push    r14
0x180002f95  push    r15
0x180002f97  sub     rsp, 88h
0x180002f9e  mov     ebp, r8d
0x180002fa1  mov     rdi, rcx
0x180002fa4  imul    rbx, rbp, 0A8h
0x180002fab  xor     esi, esi
0x180002fad  mov     r14, r9
0x180002fb0  mov     rcx, rbx; cb
0x180002fb3  mov     [rax+18h], si
0x180002fb7  call    cs:__imp_CoTaskMemAlloc
0x180002fbd  mov     [rdi+8], rax
0x180002fc1  test    rax, rax
0x180002fc4  jnz     short loc_18000300B
0x180002fc6  test    byte ptr cs:_bidGblFlags, 2
0x180002fcd  mov     ebx, 8007000Eh
0x180002fd2  jz      short loc_180003003
0x180002fd4  mov     rax, cs:off_180048448; "<CMetaData::mdGetColumnsInfo|ADO|ERR>  "...
0x180002fdb  test    rax, rax
0x180002fde  jz      short loc_180003003
0x180002fe0  mov     r8, cs:off_180048448; "<CMetaData::mdGetColumnsInfo|ADO|ERR>  "...
0x180002fe7  mov     r9d, ebx
0x180002fea  mov     rcx, cs:off_1800481B8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180002ff1  mov     edx, 84000h
0x180002ff6  mov     [rsp+0B8h+var_98], 210h
0x180002ffe  call    _bidTraceW
0x180003003  mov     ecx, ebx; int
0x180003005  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000300b  mov     r8, rbx; Size
0x18000300e  xor     edx, edx; Val
0x180003010  mov     rcx, rax; void *
0x180003013  call    memset_0
0x180003018  xor     r15d, r15d
0x18000301b  xor     ebx, ebx
0x18000301d  test    ebp, ebp
0x18000301f  jz      short loc_18000309B
0x180003021  movzx   eax, r15w
0x180003025  lea     r9, [rsp+0B8h+arg_10]; unsigned __int16 *
0x18000302d  movzx   r8d, bx; unsigned __int16
0x180003031  lea     rdx, [rsp+0B8h+var_88]; struct tagDBCOLUMNINFO
0x180003036  lea     rcx, [rax+rax*4]
0x18000303a  add     rcx, rcx
0x18000303d  movups  xmm0, xmmword ptr [r14+rcx*8]
0x180003042  movups  xmm1, xmmword ptr [r14+rcx*8+10h]
0x180003048  movaps  xmmword ptr [rsp+0B8h+var_88.pwszName], xmm0
0x18000304d  movups  xmm0, xmmword ptr [r14+rcx*8+20h]
0x180003053  movaps  xmmword ptr [rsp+0B8h+var_88.iOrdinal], xmm1
0x180003058  movups  xmm1, xmmword ptr [r14+rcx*8+30h]
0x18000305e  movaps  xmmword ptr [rsp+0B8h+var_88.ulColumnSize], xmm0
0x180003063  movups  xmm0, xmmword ptr [r14+rcx*8+40h]
0x180003069  mov     rcx, rdi; this
0x18000306c  movaps  xmmword ptr [rsp+0B8h+var_88.columnid.uGuid], xmm1
0x180003071  movaps  xmmword ptr [rsp+0B8h+var_88.columnid.eKind], xmm0
0x180003076  call    ?mdGetColInfo@CMetaData@@AEAAHUtagDBCOLUMNINFO@@GPEAG@Z; CMetaData::mdGetColInfo(tagDBCOLUMNINFO,ushort,ushort *)
0x18000307b  test    eax, eax
0x18000307d  lea     ecx, [rbx+1]
0x180003080  cmovz   cx, bx
0x180003084  inc     r15w
0x180003088  movzx   eax, r15w
0x18000308c  movzx   ebx, cx
0x18000308f  cmp     eax, ebp
0x180003091  jb      short loc_180003021
0x180003093  movzx   esi, [rsp+0B8h+arg_10]
0x18000309b  mov     [rdi], bx
0x18000309e  sub     bx, si
0x1800030a1  xor     eax, eax
0x1800030a3  mov     [rdi+2], bx
0x1800030a7  mov     [rdi+4], ax
0x1800030ab  add     rsp, 88h
0x1800030b2  pop     r15
0x1800030b4  pop     r14
0x1800030b6  pop     rdi
0x1800030b7  pop     rsi
0x1800030b8  pop     rbp
0x1800030b9  pop     rbx
0x1800030ba  retn
```
