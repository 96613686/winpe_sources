# MsvpComputeSaltedHashedPassword

- ea: `0x1800085e0`
- end: `0x18000875a`
- name: `MsvpComputeSaltedHashedPassword`
- size: `378`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008fe0`

## callees

- `0x180001cdc`
- `0x180001d24`
- `0x1800085e0`
- `0x18000c498`
- `0x18000c560`
- `0x18000d010`

## import_xrefs

- `ntdll!RtlDowncaseUnicodeString` at `0x18000862c`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000862c`
- `ntdll!RtlFreeUnicodeString` at `0x180008702`
- `ntdll!RtlFreeUnicodeString` at `0x180008702`
- `CRYPTSP!SystemFunction007` at `0x1800086a3`
- `CRYPTSP!SystemFunction007` at `0x1800086a3`
- `cryptdll!PBKDF2` at `0x1800086d7`
- `cryptdll!PBKDF2` at `0x1800086d7`

## string_xrefs

- `0x180008708`: `MsvpComputeSaltedHashedPassword`

## pseudocode

```c
__int64 __fastcall MsvpComputeSaltedHashedPassword(_OWORD *a1, _OWORD *a2, const UNICODE_STRING *a3, int a4)
{
  NTSTATUS v7; // ebx
  struct _UNICODE_STRING UniDest; // [rsp+40h] [rbp-40h] BYREF
  __int128 v10; // [rsp+50h] [rbp-30h] BYREF
  __int128 v11; // [rsp+60h] [rbp-20h] BYREF

  v10 = 0;
  UniDest = 0;
  v11 = 0;
  v7 = RtlDowncaseUnicodeString(&UniDest, a3, 1u);
  if ( v7 >= 0 )
  {
    if ( (unsigned __int16)(UniDest.Length + 16) < UniDest.Length )
    {
      v7 = -1073741675;
    }
    else
    {
      WORD1(v10) = UniDest.Length + 16;
      LOWORD(v10) = UniDest.Length + 16;
      *((_QWORD *)&v10 + 1) = (*(&GlobalConfig + 1))((unsigned __int16)(UniDest.Length + 16));
      if ( *((_QWORD *)&v10 + 1) )
      {
        **((_OWORD **)&v10 + 1) = *a2;
        memcpy_0((void *)(*((_QWORD *)&v10 + 1) + 16LL), UniDest.Buffer, UniDest.Length);
        v7 = SystemFunction007(&v10, a1);
        if ( v7 >= 0 && a4 )
        {
          v7 = PBKDF2(a1, 16, UniDest.Buffer, UniDest.Length, a4 << 10, 16, &v11);
          *a1 = v11;
        }
      }
      else
      {
        v7 = -1073741670;
      }
    }
  }
  ((void (__fastcall *)(_QWORD))xmmword_180012C60)(*((_QWORD *)&v10 + 1));
  RtlFreeUnicodeString(&UniDest);
  if ( v7 < 0 )
    NtlmTraceErrorWithStatusViaWpp("MsvpComputeSaltedHashedPassword", 0x348u, "NtlmFailure", v7);
  else
    NtlmTraceInfoViaWpp("MsvpComputeSaltedHashedPassword", 0x348u, "NtlmSuccess");
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800085e0  mov     [rsp-28h+arg_8], rbx
0x1800085e5  push    rbp
0x1800085e6  push    rsi
0x1800085e7  push    rdi
0x1800085e8  push    r14
0x1800085ea  push    r15
0x1800085ec  mov     rbp, rsp
0x1800085ef  sub     rsp, 80h
0x1800085f6  mov     rax, cs:__security_cookie
0x1800085fd  xor     rax, rsp
0x180008600  mov     [rbp+var_10], rax
0x180008604  mov     rax, r8
0x180008607  xorps   xmm0, xmm0
0x18000860a  mov     r14, rdx
0x18000860d  mov     rsi, rcx
0x180008610  xorps   xmm1, xmm1
0x180008613  lea     rcx, [rbp+UniDest]; UniDest
0x180008617  mov     rdx, rax; UniSource
0x18000861a  mov     r8b, 1; AllocateDestinationString
0x18000861d  mov     edi, r9d
0x180008620  movups  [rbp+var_30], xmm0
0x180008624  movups  xmmword ptr [rbp+UniDest.Length], xmm1
0x180008628  movups  [rbp+var_20], xmm0
0x18000862c  call    cs:__imp_RtlDowncaseUnicodeString
0x180008632  mov     ebx, eax
0x180008634  test    eax, eax
0x180008636  js      loc_1800086EE
0x18000863c  movzx   eax, [rbp+UniDest.Length]
0x180008640  mov     r15d, 10h
0x180008646  add     ax, r15w
0x18000864a  cmp     ax, [rbp+UniDest.Length]
0x18000864e  jb      loc_1800086E9
0x180008654  mov     word ptr [rbp+var_30+2], ax
0x180008658  mov     word ptr [rbp+var_30], ax
0x18000865c  movzx   ecx, ax
0x18000865f  mov     rax, qword ptr cs:?GlobalConfig@@3U_NtlmGlobalConfiguration@@A+8; _NtlmGlobalConfiguration GlobalConfig
0x180008666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000866b  mov     qword ptr [rbp+var_30+8], rax
0x18000866f  test    rax, rax
0x180008672  jnz     short loc_18000867B
0x180008674  mov     ebx, 0C000009Ah
0x180008679  jmp     short loc_1800086EE
0x18000867b  mov     rax, qword ptr [rbp+var_30+8]
0x18000867f  movups  xmm0, xmmword ptr [r14]
0x180008683  movdqu  xmmword ptr [rax], xmm0
0x180008687  mov     rcx, qword ptr [rbp+var_30+8]
0x18000868b  movzx   r8d, [rbp+UniDest.Length]; Size
0x180008690  add     rcx, r15; void *
0x180008693  mov     rdx, [rbp+UniDest.Buffer]; Src
0x180008697  call    memcpy_0
0x18000869c  mov     rdx, rsi
0x18000869f  lea     rcx, [rbp+var_30]
0x1800086a3  call    cs:__imp_SystemFunction007
0x1800086a9  mov     ebx, eax
0x1800086ab  test    eax, eax
0x1800086ad  js      short loc_1800086EE
0x1800086af  test    edi, edi
0x1800086b1  jz      short loc_1800086EE
0x1800086b3  movzx   r9d, [rbp+UniDest.Length]
0x1800086b8  lea     rax, [rbp+var_20]
0x1800086bc  mov     r8, [rbp+UniDest.Buffer]
0x1800086c0  mov     edx, r15d
0x1800086c3  mov     [rsp+80h+var_50], rax
0x1800086c8  mov     rcx, rsi
0x1800086cb  shl     edi, 0Ah
0x1800086ce  mov     [rsp+80h+var_58], r15d
0x1800086d3  mov     [rsp+80h+var_60], edi
0x1800086d7  call    cs:__imp_PBKDF2
0x1800086dd  movups  xmm0, [rbp+var_20]
0x1800086e1  mov     ebx, eax
0x1800086e3  movdqu  xmmword ptr [rsi], xmm0
0x1800086e7  jmp     short loc_1800086EE
0x1800086e9  mov     ebx, 0C0000095h
0x1800086ee  mov     rcx, qword ptr [rbp+var_30+8]
0x1800086f2  mov     rax, qword ptr cs:xmmword_180012C60
0x1800086f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086fe  lea     rcx, [rbp+UniDest]; UnicodeString
0x180008702  call    cs:__imp_RtlFreeUnicodeString
0x180008708  lea     rcx, aMsvpcomputesal_0; "MsvpComputeSaltedHashedPassword"
0x18000870f  mov     edx, 348h; unsigned int
0x180008714  test    ebx, ebx
0x180008716  js      short loc_180008726
0x180008718  lea     r8, aNtlmsuccess; "NtlmSuccess"
0x18000871f  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x180008724  jmp     short loc_180008735
0x180008726  mov     r9d, ebx; int
0x180008729  lea     r8, aNtlmfailure; "NtlmFailure"
0x180008730  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x180008735  mov     eax, ebx
0x180008737  mov     rcx, [rbp+var_10]
0x18000873b  xor     rcx, rsp; StackCookie
0x18000873e  call    __security_check_cookie
0x180008743  mov     rbx, [rsp+80h+arg_8]
0x18000874b  add     rsp, 80h
0x180008752  pop     r15
0x180008754  pop     r14
0x180008756  pop     rdi
0x180008757  pop     rsi
0x180008758  pop     rbp
0x180008759  retn
```
