# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x180014898`
- end: `0x1800149b0`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `280`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800152c0`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x180014898`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800148c7`
- `RPCRT4!UuidCreate` at `0x1800148c7`

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
0x180014898  push    rbx
0x18001489a  push    rbp
0x18001489b  push    rsi
0x18001489c  push    rdi
0x18001489d  sub     rsp, 58h
0x1800148a1  mov     rax, cs:__security_cookie
0x1800148a8  xor     rax, rsp
0x1800148ab  mov     [rsp+78h+var_38], rax
0x1800148b0  mov     rbx, rcx
0x1800148b3  mov     byte ptr [rcx+82h], 41h ; 'A'
0x1800148ba  xorps   xmm0, xmm0
0x1800148bd  lea     rcx, [rsp+78h+Uuid]; Uuid
0x1800148c2  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x1800148c7  call    cs:__imp_UuidCreate
0x1800148cd  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x1800148d2  mov     rax, 1300000000h
0x1800148dc  mov     byte ptr [rbx+81h], 11h
0x1800148e3  xor     edx, edx; Val
0x1800148e5  mov     r8d, 81h; Size
0x1800148eb  movdqa  [rsp+78h+var_58], xmm0
0x1800148f1  mov     rcx, rbx; void *
0x1800148f4  mov     [rbx+88h], rax
0x1800148fb  call    memset_0
0x180014900  xor     r11d, r11d
0x180014903  lea     rdi, [rsp+78h+var_58]
0x180014908  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; char const near * const `TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])'::`2'::s_lookupTable
0x18001490f  lea     esi, [r11+4]
0x180014913  movzx   r8d, byte ptr [rdi]
0x180014917  lea     r9, [rdi+2]
0x18001491b  movzx   r10d, byte ptr [rdi+1]
0x180014920  lea     rdi, [rdi+3]
0x180014924  mov     eax, r8d
0x180014927  and     r8b, 3
0x18001492b  shr     rax, 2
0x18001492f  shl     r8b, 4
0x180014933  movzx   ecx, r8b
0x180014937  movzx   r8d, byte ptr [r9]
0x18001493b  mov     al, [rax+rbp]
0x18001493e  mov     [r11+rbx], al
0x180014942  inc     r11d
0x180014945  mov     eax, r10d
0x180014948  and     r10b, 0Fh
0x18001494c  shr     rax, 4
0x180014950  or      rcx, rax
0x180014953  shl     r10b, 2
0x180014957  mov     al, [rcx+rbp]
0x18001495a  mov     [r11+rbx], al
0x18001495e  inc     r11d
0x180014961  mov     eax, r8d
0x180014964  movzx   ecx, r10b
0x180014968  shr     rax, 6
0x18001496c  and     r8d, 3Fh
0x180014970  or      rcx, rax
0x180014973  mov     al, [rcx+rbp]
0x180014976  mov     [r11+rbx], al
0x18001497a  inc     r11d
0x18001497d  mov     cl, [r8+rbp]
0x180014981  mov     [r11+rbx], cl
0x180014985  inc     r11d
0x180014988  add     esi, 0FFFFFFFFh
0x18001498b  jnz     short loc_180014913
0x18001498d  mov     [r11+rbx], sil
0x180014991  mov     rax, rbx
0x180014994  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18001499a  mov     rcx, [rsp+78h+var_38]
0x18001499f  xor     rcx, rsp; StackCookie
0x1800149a2  call    __security_check_cookie
0x1800149a7  add     rsp, 58h
0x1800149ab  pop     rdi
0x1800149ac  pop     rsi
0x1800149ad  pop     rbp
0x1800149ae  pop     rbx
0x1800149af  retn
```
