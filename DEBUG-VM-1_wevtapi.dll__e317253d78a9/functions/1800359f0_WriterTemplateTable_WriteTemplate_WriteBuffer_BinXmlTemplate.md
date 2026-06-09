# WriterTemplateTable::WriteTemplate(WriteBuffer &,BinXmlTemplate &)

- ea: `0x1800359f0`
- end: `0x180035bd1`
- name: `?WriteTemplate@WriterTemplateTable@@UEAAXAEAVWriteBuffer@@AEAVBinXmlTemplate@@@Z`
- size: `481`
- prototype: `void(WriterTemplateTable *__hidden this, struct WriteBuffer *, struct BinXmlTemplate *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180003780`
- `0x180013650`
- `0x180019fac`
- `0x180023548`
- `0x1800249f0`
- `0x1800303fc`
- `0x180030524`
- `0x180034d80`
- `0x1800359f0`
- `0x180038fb4`

## pseudocode

```c
void __fastcall WriterTemplateTable::WriteTemplate(
        WriterTemplateTable *this,
        struct WriteBuffer *a2,
        struct BinXmlTemplate *a3)
{
  char v6; // al
  __int64 v7; // rdx
  __int64 v8; // rsi
  unsigned int v9; // r10d
  unsigned int v10; // r8d
  unsigned int v11; // r10d
  __int64 v12; // rcx
  unsigned int *v13; // r14
  unsigned int v14; // edx
  __int64 v15; // rax
  bool v16; // r8
  unsigned int v17; // [rsp+20h] [rbp-50h] BYREF
  int v18; // [rsp+24h] [rbp-4Ch] BYREF
  __int64 v19; // [rsp+28h] [rbp-48h] BYREF
  int v20; // [rsp+30h] [rbp-40h]
  int v21; // [rsp+34h] [rbp-3Ch]
  __int128 pExceptionObject; // [rsp+38h] [rbp-38h] BYREF
  __int128 v23; // [rsp+48h] [rbp-28h]
  __int128 v24; // [rsp+58h] [rbp-18h]

  v6 = utl::_HashBytes((struct BinXmlTemplate *)((char *)a3 + 16), (const void *)0x10, (unsigned __int64)a3);
  v7 = *((_QWORD *)this + 18);
  v8 = v6 & 0x1F;
  v9 = *(_DWORD *)(*((_QWORD *)this + 1) + 4 * v8);
  v17 = v9;
  v10 = *(_DWORD *)(v7 + 32) - *(_DWORD *)(v7 + 24);
  if ( v9 >= v10 - 4 || LoopExists(v9, *(const unsigned __int8 **)(v7 + 24), v10) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ab9fd8495d9038e4932e12440453a97a_Traceguids, 13);
    }
    *(_QWORD *)&v23 = 0;
    *((_QWORD *)&v23 + 1) = -4294967283LL;
    pExceptionObject = 0;
    LODWORD(v24) = 35;
    throw (EvtException *)&pExceptionObject;
  }
  while ( v11 )
  {
    v12 = *((_QWORD *)this + 18);
    v20 = 0;
    v13 = (unsigned int *)(*(_QWORD *)(v12 + 24) + v11);
    v19 = *(_QWORD *)(v12 + 24);
    v14 = (_DWORD)v13 - *(_DWORD *)(v12 + 24) + 4;
    v21 = *(_DWORD *)(v12 + 32) - *(_DWORD *)(v12 + 24);
    UserBuffer::Advance((UserBuffer *)&v19, v14);
    pExceptionObject = 0;
    v23 = 0;
    v24 = 0;
    BinXmlTemplate::Deserialize((BinXmlTemplate *)&pExceptionObject, (struct UserBuffer *)&v19);
    v15 = v23 - *((_QWORD *)a3 + 2);
    if ( (_QWORD)v23 == *((_QWORD *)a3 + 2) )
      v15 = *((_QWORD *)&v23 + 1) - *((_QWORD *)a3 + 3);
    if ( !v15 )
    {
      WriteBuffer::Write(a2, &v17, 4u);
      return;
    }
    v11 = *v13;
    v17 = *v13;
  }
  v18 = *((_DWORD *)a2 + 4) + 4;
  WriteBuffer::Write(a2, &v18, 4u);
  WriteBuffer::Write(a2, (const void *)(*((_QWORD *)this + 1) + 4 * v8), 4u);
  *(_DWORD *)(*((_QWORD *)this + 1) + 4 * v8) = v18;
  BinXmlTemplate::Serialize(a3, a2, v16);
}

```

## disassembly

```asm
0x1800359f0  push    rbp
0x1800359f2  push    rbx
0x1800359f3  push    rsi
0x1800359f4  push    rdi
0x1800359f5  push    r13
0x1800359f7  push    r14
0x1800359f9  push    r15
0x1800359fb  mov     rbp, rsp
0x1800359fe  sub     rsp, 70h
0x180035a02  mov     rax, cs:__security_cookie
0x180035a09  xor     rax, rsp
0x180035a0c  mov     [rbp+var_8], rax
0x180035a10  mov     rdi, rcx
0x180035a13  mov     rbx, rdx
0x180035a16  mov     edx, 10h; void *
0x180035a1b  lea     rcx, [r8+10h]; this
0x180035a1f  mov     r13, r8
0x180035a22  call    ?_HashBytes@utl@@YA_KPEBX_K@Z; utl::_HashBytes(void const *,unsigned __int64)
0x180035a27  mov     rdx, [rdi+90h]
0x180035a2e  mov     rsi, rax
0x180035a31  mov     rcx, [rdi+8]
0x180035a35  and     esi, 1Fh
0x180035a38  mov     r10d, [rcx+rsi*4]
0x180035a3c  mov     [rbp+var_50], r10d
0x180035a40  mov     r8d, [rdx+20h]
0x180035a44  sub     r8d, [rdx+18h]; unsigned int
0x180035a48  lea     eax, [r8-4]
0x180035a4c  cmp     r10d, eax
0x180035a4f  jnb     loc_180035B62
0x180035a55  mov     rdx, [rdx+18h]; unsigned __int8 *
0x180035a59  mov     ecx, r10d; unsigned int
0x180035a5c  call    ?LoopExists@@YA_NKPEBEK@Z; LoopExists(ulong,uchar const *,ulong)
0x180035a61  test    al, al
0x180035a63  jnz     loc_180035B62
0x180035a69  test    r10d, r10d
0x180035a6c  jz      loc_180035B1A
0x180035a72  mov     rcx, [rdi+90h]
0x180035a79  mov     r14d, r10d
0x180035a7c  mov     [rbp+var_40], 0
0x180035a83  mov     rax, [rcx+18h]
0x180035a87  add     r14, rax
0x180035a8a  mov     [rbp+var_48], rax
0x180035a8e  mov     eax, [rcx+20h]
0x180035a91  mov     edx, r14d
0x180035a94  sub     edx, [rcx+18h]
0x180035a97  sub     eax, [rcx+18h]
0x180035a9a  add     edx, 4; unsigned int
0x180035a9d  lea     rcx, [rbp+var_48]; this
0x180035aa1  mov     [rbp+var_3C], eax
0x180035aa4  call    ?Advance@UserBuffer@@QEAAXK@Z; UserBuffer::Advance(ulong)
0x180035aa9  xorps   xmm0, xmm0
0x180035aac  lea     rdx, [rbp+var_48]; struct UserBuffer *
0x180035ab0  xorps   xmm1, xmm1
0x180035ab3  lea     rcx, [rbp+pExceptionObject]; this
0x180035ab7  movdqu  [rbp+pExceptionObject], xmm0
0x180035abc  movups  [rbp+var_28], xmm0
0x180035ac0  movdqu  [rbp+var_18], xmm1
0x180035ac5  call    ?Deserialize@BinXmlTemplate@@QEAAXAEAVUserBuffer@@@Z; BinXmlTemplate::Deserialize(UserBuffer &)
0x180035aca  mov     rax, qword ptr [rbp+var_28]
0x180035ace  sub     rax, [r13+10h]
0x180035ad2  jnz     short loc_180035ADC
0x180035ad4  mov     rax, qword ptr [rbp+var_28+8]
0x180035ad8  sub     rax, [r13+18h]
0x180035adc  test    rax, rax
0x180035adf  jz      short loc_180035AED
0x180035ae1  mov     r10d, [r14]
0x180035ae4  mov     [rbp+var_50], r10d
0x180035ae8  jmp     loc_180035A69
0x180035aed  mov     r8d, 4; unsigned int
0x180035af3  lea     rdx, [rbp+var_50]; void *
0x180035af7  mov     rcx, rbx; this
0x180035afa  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035aff  mov     rcx, [rbp+var_8]
0x180035b03  xor     rcx, rsp; StackCookie
0x180035b06  call    __security_check_cookie
0x180035b0b  add     rsp, 70h
0x180035b0f  pop     r15
0x180035b11  pop     r14
0x180035b13  pop     r13
0x180035b15  pop     rdi
0x180035b16  pop     rsi
0x180035b17  pop     rbx
0x180035b18  pop     rbp
0x180035b19  retn
0x180035b1a  mov     eax, [rbx+10h]
0x180035b1d  lea     rdx, [rbp+var_4C]; void *
0x180035b21  add     eax, 4
0x180035b24  mov     r8d, 4; unsigned int
0x180035b2a  mov     rcx, rbx; this
0x180035b2d  mov     [rbp+var_4C], eax
0x180035b30  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035b35  mov     rax, [rdi+8]
0x180035b39  mov     r8d, 4; unsigned int
0x180035b3f  mov     rcx, rbx; this
0x180035b42  lea     rdx, [rax+rsi*4]; void *
0x180035b46  call    ?Write@WriteBuffer@@QEAAXQEBXK@Z; WriteBuffer::Write(void const * const,ulong)
0x180035b4b  mov     rdx, [rdi+8]
0x180035b4f  mov     rcx, r13; this
0x180035b52  mov     eax, [rbp+var_4C]
0x180035b55  mov     [rdx+rsi*4], eax
0x180035b58  mov     rdx, rbx; struct WriteBuffer *
0x180035b5b  call    ?Serialize@BinXmlTemplate@@QEBAXAEAVWriteBuffer@@_N@Z; BinXmlTemplate::Serialize(WriteBuffer &,bool)
0x180035b60  jmp     short loc_180035AFF
0x180035b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180035b69  lea     rax, WPP_GLOBAL_Control
0x180035b70  mov     ebx, 0Dh
0x180035b75  cmp     rcx, rax
0x180035b78  jz      short loc_180035B9F
0x180035b7a  test    dword ptr [rcx+1Ch], 200h
0x180035b81  jz      short loc_180035B9F
0x180035b83  cmp     byte ptr [rcx+19h], 2
0x180035b87  jb      short loc_180035B9F
0x180035b89  mov     rcx, [rcx+10h]
0x180035b8d  lea     edx, [rbx-3]
0x180035b90  mov     r9d, ebx
0x180035b93  lea     r8, WPP_ab9fd8495d9038e4932e12440453a97a_Traceguids
0x180035b9a  call    WPP_SF_D
0x180035b9f  xorps   xmm0, xmm0
0x180035ba2  mov     qword ptr [rbp+var_28], 0
0x180035baa  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180035bb1  mov     dword ptr [rbp+var_28+8], ebx
0x180035bb4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180035bb8  mov     dword ptr [rbp+var_28+0Ch], 0FFFFFFFFh
0x180035bbf  movdqu  [rbp+pExceptionObject], xmm0
0x180035bc4  mov     dword ptr [rbp+var_18], 23h ; '#'
0x180035bcb  call    _CxxThrowException_0
```
