# LookUpTableFlushComplete

- ea: `0x140065bc8`
- end: `0x140065fa6`
- name: `LookUpTableFlushComplete`
- size: `990`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140066040`
- `0x1400660d0`
- `0x140066140`
- `0x140066384`

## callees

- `0x1400014b0`
- `0x140047b54`
- `0x140047e50`
- `0x140065bc8`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(__int64 a1)
{
  __int64 result; // rax
  unsigned int v2; // edi

  result = *(unsigned int *)(a1 + 256);
  v2 = 0;
  if ( (_DWORD)result )
  {
    if ( *(_DWORD *)(a1 + 312) > (unsigned int)result || !*(_QWORD *)(a1 + 296) )
      *(_DWORD *)(a1 + 312) = result;
    if ( *(_DWORD *)(a1 + 308) < (unsigned int)result )
      *(_DWORD *)(a1 + 308) = result;
    *(__m128i *)(a1 + 288) = _mm_add_epi64(
                               _mm_unpacklo_epi64((__m128i)(unsigned __int64)result, (__m128i)1uLL),
                               _mm_loadu_si128((const __m128i *)(a1 + 288)));
    if ( *(_QWORD *)(a1 + 288) )
    {
      if ( (unsigned int)dword_14005E100 > 5
        && (qword_14005E110 & 0x200000000000LL) != 0
        && (qword_14005E118 & 0x200000000000LL) == qword_14005E118 )
      {
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          *(_QWORD *)(*(_QWORD *)(a1 + 344) + 8LL),
          (__int64)word_140058EB2);
      }
      *(_OWORD *)(a1 + 288) = 0;
      *(_OWORD *)(a1 + 304) = 0;
      *(_QWORD *)(a1 + 320) = 0;
    }
    do
      result = FlushLookUpTableBucket(a1, v2++);
    while ( v2 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x140065bc8  mov     [rsp-8+arg_8], rbx
0x140065bcd  mov     [rsp-8+arg_10], rsi
0x140065bd2  push    rbp
0x140065bd3  push    rdi
0x140065bd4  push    r14
0x140065bd6  lea     rbp, [rsp-90h]
0x140065bde  sub     rsp, 230h
0x140065be5  mov     rax, cs:__security_cookie
0x140065bec  xor     rax, rsp
0x140065bef  mov     [rbp+0A0h+var_18], rax
0x140065bf6  mov     eax, [rcx+100h]
0x140065bfc  xor     edi, edi
0x140065bfe  mov     rbx, rcx
0x140065c01  test    eax, eax
0x140065c03  jz      loc_140065F7E
0x140065c09  cmp     [rcx+138h], eax
0x140065c0f  ja      short loc_140065C1A
0x140065c11  cmp     [rcx+128h], rdi
0x140065c18  jnz     short loc_140065C20
0x140065c1a  mov     [rcx+138h], eax
0x140065c20  cmp     [rcx+134h], eax
0x140065c26  jnb     short loc_140065C2E
0x140065c28  mov     [rcx+134h], eax
0x140065c2e  mov     esi, 1
0x140065c33  movq    xmm1, rax
0x140065c38  movq    xmm0, rsi
0x140065c3d  lea     r14d, [rsi+1Fh]
0x140065c41  punpcklqdq xmm1, xmm0
0x140065c45  movdqu  xmm0, xmmword ptr [rcx+120h]
0x140065c4d  paddq   xmm1, xmm0
0x140065c51  movdqu  xmmword ptr [rcx+120h], xmm1
0x140065c59  cmp     [rcx+120h], rdi
0x140065c60  jz      loc_140065F6D
0x140065c66  mov     eax, cs:dword_14005E100
0x140065c6c  cmp     eax, 5
0x140065c6f  jbe     loc_140065F53
0x140065c75  mov     rcx, cs:qword_14005E118
0x140065c7c  mov     rdx, 200000000000h
0x140065c86  mov     rax, cs:qword_14005E110
0x140065c8d  test    rdx, rax
0x140065c90  jz      loc_140065F53
0x140065c96  mov     rax, rcx
0x140065c99  and     rax, rdx
0x140065c9c  cmp     rax, rcx
0x140065c9f  jnz     loc_140065F53
0x140065ca5  lea     ecx, [rsi+29h]
0x140065ca8  mov     [rbp+0A0h+var_120], 4
0x140065cac  lea     rax, aSummarycount; "SummaryCount"
0x140065cb3  mov     [rbp+0A0h+var_A0], cx
0x140065cb7  mov     [rbp+0A0h+var_B8], rax
0x140065cbb  lea     eax, [rsi+17h]
0x140065cbe  mov     [rbp+0A0h+var_B0], ax
0x140065cc2  mov     eax, [rbx+144h]
0x140065cc8  mov     [rbp+0A0h+var_108], rax
0x140065ccc  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x140065cd3  mov     [rbp+0A0h+var_A8], rax
0x140065cd7  mov     eax, [rbx+140h]
0x140065cdd  mov     [rbp+0A0h+var_100], rax
0x140065ce1  lea     rax, aNumallocationf; "NumAllocationFailures"
0x140065ce8  mov     [rbp+0A0h+var_98], rax
0x140065cec  mov     eax, [rbx+13Ch]
0x140065cf2  mov     [rbp+0A0h+var_F8], rax
0x140065cf6  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x140065cfd  mov     [rbp+0A0h+var_88], rax
0x140065d01  mov     eax, [rbx+138h]
0x140065d07  mov     [rbp+0A0h+var_F0], rax
0x140065d0b  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x140065d12  mov     [rbp+0A0h+var_78], rax
0x140065d16  mov     eax, [rbx+134h]
0x140065d1c  mov     [rbp+0A0h+var_E8], rax
0x140065d20  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x140065d27  mov     [rbp+0A0h+var_68], rax
0x140065d2b  mov     rax, [rbx+120h]
0x140065d32  mov     [rbp+0A0h+var_E0], rax
0x140065d36  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x140065d3d  mov     [rbp+0A0h+var_58], rax
0x140065d41  lea     eax, [rsi+25h]
0x140065d44  mov     [rbp+0A0h+var_50], ax
0x140065d48  mov     eax, [rbx+130h]
0x140065d4e  mov     [rbp+0A0h+var_D8], rax
0x140065d52  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x140065d59  mov     [rbp+0A0h+var_48], rax
0x140065d5d  mov     rax, [rbx+128h]
0x140065d64  mov     [rbp+0A0h+var_D0], rax
0x140065d68  lea     rax, aNumflushes; "NumFlushes"
0x140065d6f  mov     [rbp+0A0h+var_38], rax
0x140065d73  lea     eax, [rsi+13h]
0x140065d76  mov     [rbp+0A0h+var_30], ax
0x140065d7a  mov     rax, [rbx+158h]
0x140065d81  mov     [rbp+0A0h+var_90], cx
0x140065d85  mov     [rbp+0A0h+var_80], cx
0x140065d89  lea     ecx, [rsi+21h]
0x140065d8c  mov     [rbp+0A0h+var_114], esi
0x140065d8f  mov     [rbp+0A0h+var_11F], 4
0x140065d93  mov     [rbp+0A0h+var_11E], 4
0x140065d97  mov     [rbp+0A0h+var_11D], 4
0x140065d9b  mov     [rbp+0A0h+var_11C], 4
0x140065d9f  mov     [rbp+0A0h+var_70], cx
0x140065da3  mov     [rbp+0A0h+var_11B], 4
0x140065da7  mov     [rbp+0A0h+var_60], cx
0x140065dab  mov     [rbp+0A0h+var_11A], 4
0x140065daf  mov     [rbp+0A0h+var_119], 4
0x140065db3  mov     [rbp+0A0h+var_40], r14w
0x140065db8  mov     [rbp+0A0h+var_118], 4
0x140065dbc  mov     rcx, [rax+8]
0x140065dc0  lea     rax, [rbp+0A0h+var_28]
0x140065dc4  mov     [rbp+0A0h+var_C8], rax
0x140065dc8  lea     rax, [rbp+0A0h+var_120]
0x140065dcc  mov     [rsp+240h+var_128], rax
0x140065dd4  lea     rax, [rbp+0A0h+var_114]
0x140065dd8  mov     [rsp+240h+var_130], rax
0x140065de0  lea     rax, [rbp+0A0h+var_B8]
0x140065de4  movups  xmm0, xmmword ptr [rcx-10h]
0x140065de8  mov     [rsp+240h+var_138], rax
0x140065df0  lea     rax, [rbp+0A0h+var_11F]
0x140065df4  mov     [rsp+240h+var_140], rax
0x140065dfc  lea     rax, [rbp+0A0h+var_108]
0x140065e00  mov     [rsp+240h+var_148], rax
0x140065e08  lea     rax, [rbp+0A0h+var_A8]
0x140065e0c  mov     [rsp+240h+var_150], rax
0x140065e14  lea     rax, [rbp+0A0h+var_11E]
0x140065e18  movdqu  [rbp+0A0h+var_28], xmm0
0x140065e1d  mov     [rbp+0A0h+var_117], dil
0x140065e21  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x140065e28  mov     [rbp+0A0h+var_10C], 12Ch
0x140065e2f  mov     [rbp+0A0h+var_C0], 1000000h
0x140065e37  mov     [rsp+240h+var_158], rax
0x140065e3f  lea     rdx, word_140058EB2
0x140065e46  lea     rax, [rbp+0A0h+var_100]
0x140065e4a  mov     [rsp+240h+var_160], rax
0x140065e52  lea     rax, [rbp+0A0h+var_98]
0x140065e56  mov     [rsp+240h+var_168], rax
0x140065e5e  lea     rax, [rbp+0A0h+var_11D]
0x140065e62  mov     [rsp+240h+var_170], rax
0x140065e6a  lea     rax, [rbp+0A0h+var_F8]
0x140065e6e  mov     [rsp+240h+var_178], rax
0x140065e76  lea     rax, [rbp+0A0h+var_88]
0x140065e7a  mov     [rsp+240h+var_180], rax
0x140065e82  lea     rax, [rbp+0A0h+var_11C]
0x140065e86  mov     [rsp+240h+var_188], rax
0x140065e8e  lea     rax, [rbp+0A0h+var_F0]
0x140065e92  mov     [rsp+240h+var_190], rax
0x140065e9a  lea     rax, [rbp+0A0h+var_78]
0x140065e9e  mov     [rsp+240h+var_198], rax
0x140065ea6  lea     rax, [rbp+0A0h+var_11B]
0x140065eaa  mov     [rsp+240h+var_1A0], rax
0x140065eb2  lea     rax, [rbp+0A0h+var_E8]
0x140065eb6  mov     [rsp+240h+var_1A8], rax
0x140065ebe  lea     rax, [rbp+0A0h+var_68]
0x140065ec2  mov     [rsp+240h+var_1B0], rax
0x140065eca  lea     rax, [rbp+0A0h+var_11A]
0x140065ece  mov     [rsp+240h+var_1B8], rax
0x140065ed6  lea     rax, [rbp+0A0h+var_E0]
0x140065eda  mov     [rsp+240h+var_1C0], rax
0x140065ee2  lea     rax, [rbp+0A0h+var_58]
0x140065ee6  mov     [rsp+240h+var_1C8], rax
0x140065eeb  lea     rax, [rbp+0A0h+var_119]
0x140065eef  mov     [rsp+240h+var_1D0], rax
0x140065ef4  lea     rax, [rbp+0A0h+var_D8]
0x140065ef8  mov     [rsp+240h+var_1D8], rax
0x140065efd  lea     rax, [rbp+0A0h+var_48]
0x140065f01  mov     [rsp+240h+var_1E0], rax
0x140065f06  lea     rax, [rbp+0A0h+var_118]
0x140065f0a  mov     [rsp+240h+var_1E8], rax
0x140065f0f  lea     rax, [rbp+0A0h+var_D0]
0x140065f13  mov     [rsp+240h+var_1F0], rax
0x140065f18  lea     rax, [rbp+0A0h+var_38]
0x140065f1c  mov     [rsp+240h+var_1F8], rax
0x140065f21  lea     rax, [rbp+0A0h+var_C8]
0x140065f25  mov     [rsp+240h+var_200], rax
0x140065f2a  lea     rax, [rbp+0A0h+var_117]
0x140065f2e  mov     [rsp+240h+var_208], rax
0x140065f33  lea     rax, [rbp+0A0h+var_110]
0x140065f37  mov     [rsp+240h+var_210], rax
0x140065f3c  lea     rax, [rbp+0A0h+var_10C]
0x140065f40  mov     [rsp+240h+var_218], rax
0x140065f45  lea     rax, [rbp+0A0h+var_C0]
0x140065f49  mov     [rsp+240h+var_220], rax
0x140065f4e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x140065f53  xorps   xmm0, xmm0
0x140065f56  xor     eax, eax
0x140065f58  movups  xmmword ptr [rbx+120h], xmm0
0x140065f5f  movups  xmmword ptr [rbx+130h], xmm0
0x140065f66  mov     [rbx+140h], rax
0x140065f6d  mov     edx, edi
0x140065f6f  mov     rcx, rbx
0x140065f72  call    FlushLookUpTableBucket
0x140065f77  add     edi, esi
0x140065f79  cmp     edi, r14d
0x140065f7c  jb      short loc_140065F6D
0x140065f7e  mov     rcx, [rbp+0A0h+var_18]
0x140065f85  xor     rcx, rsp; StackCookie
0x140065f88  call    __security_check_cookie
0x140065f8d  lea     r11, [rsp+240h+var_10]
0x140065f95  mov     rbx, [r11+28h]
0x140065f99  mov     rsi, [r11+30h]
0x140065f9d  mov     rsp, r11
0x140065fa0  pop     r14
0x140065fa2  pop     rdi
0x140065fa3  pop     rbp
0x140065fa4  retn
```
