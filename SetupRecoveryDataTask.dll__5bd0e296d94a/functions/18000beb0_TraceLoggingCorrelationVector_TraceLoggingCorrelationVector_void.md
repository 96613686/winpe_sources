# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x18000beb0`
- end: `0x18000bfc8`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `280`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c134`

## callees

- `0x18000beb0`
- `0x18000c5e2`
- `0x18000c610`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18000bedf`
- `RPCRT4!UuidCreate` at `0x18000bedf`

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
0x18000beb0  push    rbx
0x18000beb2  push    rbp
0x18000beb3  push    rsi
0x18000beb4  push    rdi
0x18000beb5  sub     rsp, 58h
0x18000beb9  mov     rax, cs:__security_cookie
0x18000bec0  xor     rax, rsp
0x18000bec3  mov     [rsp+78h+var_38], rax
0x18000bec8  mov     rbx, rcx
0x18000becb  mov     byte ptr [rcx+82h], 41h ; 'A'
0x18000bed2  xorps   xmm0, xmm0
0x18000bed5  lea     rcx, [rsp+78h+Uuid]; Uuid
0x18000beda  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x18000bedf  call    cs:__imp_UuidCreate
0x18000bee5  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x18000beea  mov     rax, 1300000000h
0x18000bef4  mov     byte ptr [rbx+81h], 11h
0x18000befb  xor     edx, edx; Val
0x18000befd  mov     r8d, 81h; Size
0x18000bf03  movdqa  [rsp+78h+var_58], xmm0
0x18000bf09  mov     rcx, rbx; void *
0x18000bf0c  mov     [rbx+88h], rax
0x18000bf13  call    memset_0
0x18000bf18  xor     r11d, r11d
0x18000bf1b  lea     rdi, [rsp+78h+var_58]
0x18000bf20  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; char const near * const `TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])'::`2'::s_lookupTable
0x18000bf27  lea     esi, [r11+4]
0x18000bf2b  movzx   r8d, byte ptr [rdi]
0x18000bf2f  lea     r9, [rdi+2]
0x18000bf33  movzx   r10d, byte ptr [rdi+1]
0x18000bf38  lea     rdi, [rdi+3]
0x18000bf3c  mov     eax, r8d
0x18000bf3f  and     r8b, 3
0x18000bf43  shr     rax, 2
0x18000bf47  shl     r8b, 4
0x18000bf4b  movzx   ecx, r8b
0x18000bf4f  movzx   r8d, byte ptr [r9]
0x18000bf53  mov     al, [rax+rbp]
0x18000bf56  mov     [r11+rbx], al
0x18000bf5a  inc     r11d
0x18000bf5d  mov     eax, r10d
0x18000bf60  and     r10b, 0Fh
0x18000bf64  shr     rax, 4
0x18000bf68  or      rcx, rax
0x18000bf6b  shl     r10b, 2
0x18000bf6f  mov     al, [rcx+rbp]
0x18000bf72  mov     [r11+rbx], al
0x18000bf76  inc     r11d
0x18000bf79  mov     eax, r8d
0x18000bf7c  movzx   ecx, r10b
0x18000bf80  shr     rax, 6
0x18000bf84  and     r8d, 3Fh
0x18000bf88  or      rcx, rax
0x18000bf8b  mov     al, [rcx+rbp]
0x18000bf8e  mov     [r11+rbx], al
0x18000bf92  inc     r11d
0x18000bf95  mov     cl, [r8+rbp]
0x18000bf99  mov     [r11+rbx], cl
0x18000bf9d  inc     r11d
0x18000bfa0  add     esi, 0FFFFFFFFh
0x18000bfa3  jnz     short loc_18000BF2B
0x18000bfa5  mov     [r11+rbx], sil
0x18000bfa9  mov     rax, rbx
0x18000bfac  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18000bfb2  mov     rcx, [rsp+78h+var_38]
0x18000bfb7  xor     rcx, rsp; StackCookie
0x18000bfba  call    __security_check_cookie
0x18000bfbf  add     rsp, 58h
0x18000bfc3  pop     rdi
0x18000bfc4  pop     rsi
0x18000bfc5  pop     rbp
0x18000bfc6  pop     rbx
0x18000bfc7  retn
```
