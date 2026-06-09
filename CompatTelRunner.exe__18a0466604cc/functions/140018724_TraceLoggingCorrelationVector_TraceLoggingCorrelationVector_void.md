# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x140018724`
- end: `0x14001883c`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `280`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400184cc`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x140018724`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x140018753`
- `RPCRT4!UuidCreate` at `0x140018753`

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
    LOBYTE(v10) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[v11 & 0x3F];
    *((_BYTE *)this + v13) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[((unsigned __int64)v11 >> 6)
                                                                        | (unsigned __int8)(4 * (v8 & 0xF))];
    v14 = (unsigned int)(v13 + 1);
    *((_BYTE *)this + v14) = v10;
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
0x140018724  push    rbx
0x140018726  push    rbp
0x140018727  push    rsi
0x140018728  push    rdi
0x140018729  sub     rsp, 58h
0x14001872d  mov     rax, cs:__security_cookie
0x140018734  xor     rax, rsp
0x140018737  mov     [rsp+78h+var_38], rax
0x14001873c  mov     rbx, rcx
0x14001873f  mov     byte ptr [rcx+82h], 41h ; 'A'
0x140018746  xorps   xmm0, xmm0
0x140018749  lea     rcx, [rsp+78h+Uuid]; Uuid
0x14001874e  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x140018753  call    cs:__imp_UuidCreate
0x140018759  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x14001875e  mov     rax, 1300000000h
0x140018768  mov     byte ptr [rbx+81h], 11h
0x14001876f  xor     edx, edx; Val
0x140018771  mov     r8d, 81h; Size
0x140018777  movdqa  [rsp+78h+var_58], xmm0
0x14001877d  mov     rcx, rbx; void *
0x140018780  mov     [rbx+88h], rax
0x140018787  call    memset_0
0x14001878c  xor     r11d, r11d
0x14001878f  lea     rdi, [rsp+78h+var_58]
0x140018794  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x14001879b  lea     esi, [r11+4]
0x14001879f  movzx   r8d, byte ptr [rdi]
0x1400187a3  lea     r9, [rdi+2]
0x1400187a7  movzx   r10d, byte ptr [rdi+1]
0x1400187ac  lea     rdi, [rdi+3]
0x1400187b0  mov     eax, r8d
0x1400187b3  and     r8b, 3
0x1400187b7  shr     rax, 2
0x1400187bb  shl     r8b, 4
0x1400187bf  movzx   ecx, r8b
0x1400187c3  movzx   r8d, byte ptr [r9]
0x1400187c7  mov     al, [rax+rbp]
0x1400187ca  mov     [r11+rbx], al
0x1400187ce  inc     r11d
0x1400187d1  mov     eax, r10d
0x1400187d4  and     r10b, 0Fh
0x1400187d8  shr     rax, 4
0x1400187dc  or      rcx, rax
0x1400187df  shl     r10b, 2
0x1400187e3  mov     al, [rcx+rbp]
0x1400187e6  mov     [r11+rbx], al
0x1400187ea  inc     r11d
0x1400187ed  mov     eax, r8d
0x1400187f0  movzx   ecx, r10b
0x1400187f4  shr     rax, 6
0x1400187f8  and     r8d, 3Fh
0x1400187fc  or      rcx, rax
0x1400187ff  mov     al, [rcx+rbp]
0x140018802  mov     cl, [r8+rbp]
0x140018806  mov     [r11+rbx], al
0x14001880a  inc     r11d
0x14001880d  mov     [r11+rbx], cl
0x140018811  inc     r11d
0x140018814  add     esi, 0FFFFFFFFh
0x140018817  jnz     short loc_14001879F
0x140018819  mov     [r11+rbx], sil
0x14001881d  mov     rax, rbx
0x140018820  mov     word ptr [rbx+10h], 2Eh ; '.'
0x140018826  mov     rcx, [rsp+78h+var_38]
0x14001882b  xor     rcx, rsp; StackCookie
0x14001882e  call    __security_check_cookie
0x140018833  add     rsp, 58h
0x140018837  pop     rdi
0x140018838  pop     rsi
0x140018839  pop     rbp
0x14001883a  pop     rbx
0x14001883b  retn
```
