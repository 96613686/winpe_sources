# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x180011f38`
- end: `0x180012050`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `280`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800177f8`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x180011f38`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180011f67`
- `RPCRT4!UuidCreate` at `0x180011f67`

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
0x180011f38  push    rbx
0x180011f3a  push    rbp
0x180011f3b  push    rsi
0x180011f3c  push    rdi
0x180011f3d  sub     rsp, 58h
0x180011f41  mov     rax, cs:__security_cookie
0x180011f48  xor     rax, rsp
0x180011f4b  mov     [rsp+78h+var_38], rax
0x180011f50  mov     rbx, rcx
0x180011f53  mov     byte ptr [rcx+82h], 41h ; 'A'
0x180011f5a  xorps   xmm0, xmm0
0x180011f5d  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180011f62  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180011f67  call    cs:__imp_UuidCreate
0x180011f6d  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x180011f72  mov     rax, 1300000000h
0x180011f7c  mov     byte ptr [rbx+81h], 11h
0x180011f83  xor     edx, edx; Val
0x180011f85  mov     r8d, 81h; Size
0x180011f8b  movdqa  [rsp+78h+var_58], xmm0
0x180011f91  mov     rcx, rbx; void *
0x180011f94  mov     [rbx+88h], rax
0x180011f9b  call    memset_0
0x180011fa0  xor     r11d, r11d
0x180011fa3  lea     rdi, [rsp+78h+var_58]
0x180011fa8  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; char const near * const `TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])'::`2'::s_lookupTable
0x180011faf  lea     esi, [r11+4]
0x180011fb3  movzx   r8d, byte ptr [rdi]
0x180011fb7  lea     r9, [rdi+2]
0x180011fbb  movzx   r10d, byte ptr [rdi+1]
0x180011fc0  lea     rdi, [rdi+3]
0x180011fc4  mov     eax, r8d
0x180011fc7  and     r8b, 3
0x180011fcb  shr     rax, 2
0x180011fcf  shl     r8b, 4
0x180011fd3  movzx   ecx, r8b
0x180011fd7  movzx   r8d, byte ptr [r9]
0x180011fdb  mov     al, [rax+rbp]
0x180011fde  mov     [r11+rbx], al
0x180011fe2  inc     r11d
0x180011fe5  mov     eax, r10d
0x180011fe8  and     r10b, 0Fh
0x180011fec  shr     rax, 4
0x180011ff0  or      rcx, rax
0x180011ff3  shl     r10b, 2
0x180011ff7  mov     al, [rcx+rbp]
0x180011ffa  mov     [r11+rbx], al
0x180011ffe  inc     r11d
0x180012001  mov     eax, r8d
0x180012004  movzx   ecx, r10b
0x180012008  shr     rax, 6
0x18001200c  and     r8d, 3Fh
0x180012010  or      rcx, rax
0x180012013  mov     al, [rcx+rbp]
0x180012016  mov     [r11+rbx], al
0x18001201a  inc     r11d
0x18001201d  mov     cl, [r8+rbp]
0x180012021  mov     [r11+rbx], cl
0x180012025  inc     r11d
0x180012028  add     esi, 0FFFFFFFFh
0x18001202b  jnz     short loc_180011FB3
0x18001202d  mov     [r11+rbx], sil
0x180012031  mov     rax, rbx
0x180012034  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18001203a  mov     rcx, [rsp+78h+var_38]
0x18001203f  xor     rcx, rsp; StackCookie
0x180012042  call    __security_check_cookie
0x180012047  add     rsp, 58h
0x18001204b  pop     rdi
0x18001204c  pop     rsi
0x18001204d  pop     rbp
0x18001204e  pop     rbx
0x18001204f  retn
```
