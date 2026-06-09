# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x180014c7c`
- end: `0x180014d9b`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `287`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800156c8`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x180014c7c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180014cab`
- `RPCRT4!UuidCreate` at `0x180014cab`

## pseudocode

```c
TraceLoggingCorrelationVector *__fastcall TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(
        TraceLoggingCorrelationVector *this)
{
  UUID v2; // xmm0
  __int64 v3; // r11
  UUID *v4; // rdi
  int v5; // esi
  unsigned int Data1_low; // r8d
  unsigned __int8 *v7; // r9
  unsigned int v8; // r10d
  unsigned __int64 v9; // rax
  __int64 v10; // rcx
  unsigned int v11; // r8d
  __int64 v12; // r11
  __int64 v13; // r11
  __int64 v14; // r11
  TraceLoggingCorrelationVector *result; // rax
  UUID v16; // [rsp+20h] [rbp-58h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-48h] BYREF

  *((_BYTE *)this + 130) = 65;
  Uuid = 0;
  UuidCreate(&Uuid);
  v2 = Uuid;
  *((_BYTE *)this + 129) = 17;
  v16 = v2;
  *((_QWORD *)this + 17) = 0x1300000000LL;
  memset_0(this, 0, 0x81u);
  v3 = 0;
  v4 = &v16;
  v5 = 4;
  do
  {
    Data1_low = LOBYTE(v4->Data1);
    v7 = (unsigned __int8 *)&v4->Data1 + 2;
    v8 = BYTE1(v4->Data1);
    v4 = (UUID *)((char *)v4 + 3);
    v9 = Data1_low;
    v10 = (unsigned __int8)(16 * (Data1_low & 3));
    v11 = *v7;
    *((_BYTE *)this + v3) = *((_BYTE *)`TLV::Base64Encode<129>'::`2'::s_lookupTable + (v9 >> 2));
    v12 = (unsigned int)(v3 + 1);
    *((_BYTE *)this + v12) = *((_BYTE *)`TLV::Base64Encode<129>'::`2'::s_lookupTable
                             + (((unsigned __int64)v8 >> 4) | v10));
    v13 = (unsigned int)(v12 + 1);
    *((_BYTE *)this + v13) = *((_BYTE *)`TLV::Base64Encode<129>'::`2'::s_lookupTable
                             + (((unsigned __int64)v11 >> 6) | (unsigned __int8)(4 * (v8 & 0xF))));
    v14 = (unsigned int)(v13 + 1);
    *((_BYTE *)this + v14) = *((_BYTE *)`TLV::Base64Encode<129>'::`2'::s_lookupTable + (v11 & 0x3F));
    v3 = (unsigned int)(v14 + 1);
    --v5;
  }
  while ( v5 );
  *((_BYTE *)this + v3) = 0;
  result = this;
  *((_WORD *)this + 8) = 46;
  return result;
}

```

## disassembly

```asm
0x180014c7c  push    rbx
0x180014c7e  push    rbp
0x180014c7f  push    rsi
0x180014c80  push    rdi
0x180014c81  sub     rsp, 58h
0x180014c85  mov     rax, cs:__security_cookie
0x180014c8c  xor     rax, rsp
0x180014c8f  mov     [rsp+78h+var_38], rax
0x180014c94  mov     rbx, rcx
0x180014c97  mov     byte ptr [rcx+82h], 41h ; 'A'
0x180014c9e  xorps   xmm0, xmm0
0x180014ca1  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180014ca6  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180014cab  call    cs:__imp_UuidCreate
0x180014cb2  nop     dword ptr [rax+rax+00h]
0x180014cb7  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x180014cbc  mov     rax, 1300000000h
0x180014cc6  mov     byte ptr [rbx+81h], 11h
0x180014ccd  xor     edx, edx; Val
0x180014ccf  mov     r8d, 81h; Size
0x180014cd5  movdqa  [rsp+78h+var_58], xmm0
0x180014cdb  mov     rcx, rbx; void *
0x180014cde  mov     [rbx+88h], rax
0x180014ce5  call    memset_0
0x180014cea  xor     r11d, r11d
0x180014ced  lea     rdi, [rsp+78h+var_58]
0x180014cf2  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; char const near * const `TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])'::`2'::s_lookupTable
0x180014cf9  lea     esi, [r11+4]
0x180014cfd  movzx   r8d, byte ptr [rdi]
0x180014d01  lea     r9, [rdi+2]
0x180014d05  movzx   r10d, byte ptr [rdi+1]
0x180014d0a  lea     rdi, [rdi+3]
0x180014d0e  mov     eax, r8d
0x180014d11  and     r8b, 3
0x180014d15  shr     rax, 2
0x180014d19  shl     r8b, 4
0x180014d1d  movzx   ecx, r8b
0x180014d21  movzx   r8d, byte ptr [r9]
0x180014d25  mov     al, [rax+rbp]
0x180014d28  mov     [r11+rbx], al
0x180014d2c  inc     r11d
0x180014d2f  mov     eax, r10d
0x180014d32  and     r10b, 0Fh
0x180014d36  shr     rax, 4
0x180014d3a  or      rcx, rax
0x180014d3d  shl     r10b, 2
0x180014d41  mov     al, [rcx+rbp]
0x180014d44  mov     [r11+rbx], al
0x180014d48  inc     r11d
0x180014d4b  mov     eax, r8d
0x180014d4e  movzx   ecx, r10b
0x180014d52  shr     rax, 6
0x180014d56  and     r8d, 3Fh
0x180014d5a  or      rcx, rax
0x180014d5d  mov     al, [rcx+rbp]
0x180014d60  mov     [r11+rbx], al
0x180014d64  inc     r11d
0x180014d67  mov     cl, [r8+rbp]
0x180014d6b  mov     [r11+rbx], cl
0x180014d6f  inc     r11d
0x180014d72  add     esi, 0FFFFFFFFh
0x180014d75  jnz     short loc_180014CFD
0x180014d77  mov     [r11+rbx], sil
0x180014d7b  mov     rax, rbx
0x180014d7e  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180014d84  mov     rcx, [rsp+78h+var_38]
0x180014d89  xor     rcx, rsp; StackCookie
0x180014d8c  call    __security_check_cookie
0x180014d91  add     rsp, 58h
0x180014d95  pop     rdi
0x180014d96  pop     rsi
0x180014d97  pop     rbp
0x180014d98  pop     rbx
0x180014d99  retn
```
