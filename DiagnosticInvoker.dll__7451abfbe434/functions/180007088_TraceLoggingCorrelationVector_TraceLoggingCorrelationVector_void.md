# TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)

- ea: `0x180007088`
- end: `0x1800071a0`
- name: `??0TraceLoggingCorrelationVector@@QEAA@XZ`
- size: `280`
- prototype: `TraceLoggingCorrelationVector *__fastcall(TraceLoggingCorrelationVector *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007700`

## callees

- `0x180001e20`
- `0x180002ac8`
- `0x180007088`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800070b7`
- `RPCRT4!UuidCreate` at `0x1800070b7`

## string_xrefs

- `0x1800070f8`: `ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/Windows.Foundation.AsyncOperationWithProgressCompletedHandler`2<Windows.System.Diagnostics.DiagnosticActionResult, Windows.System.Diagnostics.DiagnosticActionState>`

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
0x180007088  push    rbx
0x18000708a  push    rbp
0x18000708b  push    rsi
0x18000708c  push    rdi
0x18000708d  sub     rsp, 58h
0x180007091  mov     rax, cs:__security_cookie
0x180007098  xor     rax, rsp
0x18000709b  mov     [rsp+78h+var_38], rax
0x1800070a0  mov     rbx, rcx
0x1800070a3  mov     byte ptr [rcx+82h], 41h ; 'A'
0x1800070aa  xorps   xmm0, xmm0
0x1800070ad  lea     rcx, [rsp+78h+Uuid]; Uuid
0x1800070b2  movups  xmmword ptr [rsp+78h+Uuid.Data1], xmm0
0x1800070b7  call    cs:__imp_UuidCreate
0x1800070bd  movaps  xmm0, xmmword ptr [rsp+78h+Uuid.Data1]
0x1800070c2  mov     rax, 1300000000h
0x1800070cc  mov     byte ptr [rbx+81h], 11h
0x1800070d3  xor     edx, edx; Val
0x1800070d5  mov     r8d, 81h; Size
0x1800070db  movdqa  [rsp+78h+var_58], xmm0
0x1800070e1  mov     rcx, rbx; void *
0x1800070e4  mov     [rbx+88h], rax
0x1800070eb  call    memset_0
0x1800070f0  xor     r11d, r11d
0x1800070f3  lea     rdi, [rsp+78h+var_58]
0x1800070f8  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x1800070ff  lea     esi, [r11+4]
0x180007103  movzx   r8d, byte ptr [rdi]
0x180007107  lea     r9, [rdi+2]
0x18000710b  movzx   r10d, byte ptr [rdi+1]
0x180007110  lea     rdi, [rdi+3]
0x180007114  mov     eax, r8d
0x180007117  and     r8b, 3
0x18000711b  shr     rax, 2
0x18000711f  shl     r8b, 4
0x180007123  movzx   ecx, r8b
0x180007127  movzx   r8d, byte ptr [r9]
0x18000712b  mov     al, [rax+rbp]
0x18000712e  mov     [r11+rbx], al
0x180007132  inc     r11d
0x180007135  mov     eax, r10d
0x180007138  and     r10b, 0Fh
0x18000713c  shr     rax, 4
0x180007140  or      rcx, rax
0x180007143  shl     r10b, 2
0x180007147  mov     al, [rcx+rbp]
0x18000714a  mov     [r11+rbx], al
0x18000714e  inc     r11d
0x180007151  mov     eax, r8d
0x180007154  movzx   ecx, r10b
0x180007158  shr     rax, 6
0x18000715c  and     r8d, 3Fh
0x180007160  or      rcx, rax
0x180007163  mov     al, [rcx+rbp]
0x180007166  mov     cl, [r8+rbp]
0x18000716a  mov     [r11+rbx], al
0x18000716e  inc     r11d
0x180007171  mov     [r11+rbx], cl
0x180007175  inc     r11d
0x180007178  add     esi, 0FFFFFFFFh
0x18000717b  jnz     short loc_180007103
0x18000717d  mov     [r11+rbx], sil
0x180007181  mov     rax, rbx
0x180007184  mov     word ptr [rbx+10h], 2Eh ; '.'
0x18000718a  mov     rcx, [rsp+78h+var_38]
0x18000718f  xor     rcx, rsp; StackCookie
0x180007192  call    __security_check_cookie
0x180007197  add     rsp, 58h
0x18000719b  pop     rdi
0x18000719c  pop     rsi
0x18000719d  pop     rbp
0x18000719e  pop     rbx
0x18000719f  retn
```
