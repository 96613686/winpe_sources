# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x180003f20`
- end: `0x180004038`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `280`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800041a4`

## callees

- `0x180003f20`
- `0x1800142d2`
- `0x180014310`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180003f4f`
- `RPCRT4!UuidCreate` at `0x180003f4f`

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
    *((_BYTE *)this + v3) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[v9 >> 2];
    v12 = (unsigned int)(v3 + 1);
    *((_BYTE *)this + v12) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[((unsigned __int64)v8 >> 4) | v10];
    v13 = (unsigned int)(v12 + 1);
    *((_BYTE *)this + v13) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[((unsigned __int64)v11 >> 6)
                                                                        | (unsigned __int8)(4 * (v8 & 0xF))];
    v14 = (unsigned int)(v13 + 1);
    *((_BYTE *)this + v14) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[v11 & 0x3F];
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
0x180003f20  push    rbx
0x180003f22  push    rbp
0x180003f23  push    rsi
0x180003f24  push    rdi
0x180003f25  sub     rsp, 58h
0x180003f29  mov     rax, cs:__security_cookie
0x180003f30  xor     rax, rsp
0x180003f33  mov     [rsp+78h+var_38], rax
0x180003f38  mov     rbx, rcx
0x180003f3b  mov     byte ptr [rcx+82h], 41h ; 'A'
0x180003f42  xorps   xmm0, xmm0
0x180003f45  lea     rcx, [rsp+78h+Uuid]; Uuid
0x180003f4a  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x180003f4f  call    cs:__imp_UuidCreate
0x180003f55  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x180003f5a  mov     rax, 1300000000h
0x180003f64  mov     byte ptr [rbx+81h], 11h
0x180003f6b  xor     edx, edx; Val
0x180003f6d  mov     r8d, 81h; Size
0x180003f73  movdqa  [rsp+78h+var_58], xmm0
0x180003f79  mov     rcx, rbx; void *
0x180003f7c  mov     [rbx+88h], rax
0x180003f83  call    memset_0
0x180003f88  xor     r11d, r11d
0x180003f8b  lea     rdi, [rsp+78h+var_58]
0x180003f90  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x180003f97  lea     esi, [r11+4]
0x180003f9b  movzx   r8d, byte ptr [rdi]
0x180003f9f  lea     r9, [rdi+2]
0x180003fa3  movzx   r10d, byte ptr [rdi+1]
0x180003fa8  lea     rdi, [rdi+3]
0x180003fac  mov     eax, r8d
0x180003faf  and     r8b, 3
0x180003fb3  shr     rax, 2
0x180003fb7  shl     r8b, 4
0x180003fbb  movzx   ecx, r8b
0x180003fbf  movzx   r8d, byte ptr [r9]
0x180003fc3  mov     al, [rax+rbp]
0x180003fc6  mov     [r11+rbx], al
0x180003fca  inc     r11d
0x180003fcd  mov     eax, r10d
0x180003fd0  and     r10b, 0Fh
0x180003fd4  shr     rax, 4
0x180003fd8  or      rcx, rax
0x180003fdb  shl     r10b, 2
0x180003fdf  mov     al, [rcx+rbp]
0x180003fe2  mov     [r11+rbx], al
0x180003fe6  inc     r11d
0x180003fe9  mov     eax, r8d
0x180003fec  movzx   ecx, r10b
0x180003ff0  shr     rax, 6
0x180003ff4  and     r8d, 3Fh
0x180003ff8  or      rcx, rax
0x180003ffb  mov     al, [rcx+rbp]
0x180003ffe  mov     [r11+rbx], al
0x180004002  inc     r11d
0x180004005  mov     cl, [r8+rbp]
0x180004009  mov     [r11+rbx], cl
0x18000400d  inc     r11d
0x180004010  add     esi, 0FFFFFFFFh
0x180004013  jnz     short loc_180003F9B
0x180004015  mov     [r11+rbx], sil
0x180004019  mov     rax, rbx
0x18000401c  mov     word ptr [rbx+10h], 2Eh ; '.'
0x180004022  mov     rcx, [rsp+78h+var_38]
0x180004027  xor     rcx, rsp; StackCookie
0x18000402a  call    __security_check_cookie
0x18000402f  add     rsp, 58h
0x180004033  pop     rdi
0x180004034  pop     rsi
0x180004035  pop     rbp
0x180004036  pop     rbx
0x180004037  retn
```
