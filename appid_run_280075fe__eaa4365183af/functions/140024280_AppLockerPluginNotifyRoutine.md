# AppLockerPluginNotifyRoutine

- ea: `0x140024280`
- end: `0x14002448c`
- name: `AppLockerPluginNotifyRoutine`
- size: `524`
- prototype: `__int64 __fastcall(int, int, int, int, char, HANDLE, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task`

## callees

- `0x14002023c`
- `0x140020288`
- `0x140022afc`
- `0x140024280`
- `0x140031890`
- `0x140032e40`
- `0x140035c50`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140024464`
- `ntoskrnl!ZwClose` at `0x140024464`

## pseudocode

```c
__int64 __fastcall AppLockerPluginNotifyRoutine(
        _QWORD *a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        HANDLE a6,
        __int64 a7,
        __int64 a8,
        _DWORD *a9)
{
  char v12; // r12
  __int64 v13; // rcx
  const wchar_t *v14; // rax
  bool v15; // zf
  __int64 v16; // rax
  unsigned int v17; // edi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rsi
  BOOLEAN v22; // [rsp+40h] [rbp-30h] BYREF
  _BYTE v23[7]; // [rsp+41h] [rbp-2Fh] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-28h] BYREF
  __int128 v25; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v26; // [rsp+60h] [rbp-10h] BYREF

  Handle = 0;
  v22 = 0;
  v25 = 0;
  v26 = 0;
  if ( (int)AiOpenTokenByProcessId(a5, &Handle) < 0 || (int)SrpIsTokenService(Handle, &v22) < 0 )
    goto LABEL_25;
  v12 = 0;
  v13 = 0x4B71A17234B165B1LL - *a1;
  if ( *a1 == 0x4B71A17234B165B1LL )
    v13 = 0x7C91549C5732B395LL - a1[1];
  if ( v13 )
  {
    v16 = *a1 - 0x4896EF1A58125A50LL;
    v15 = *a1 == 0x4896EF1A58125A50LL;
    v26 = *(UNICODE_STRING *)*(_QWORD *)(a7 + 48);
    if ( v15 )
      v16 = a1[1] - 0x6CCAB39AC6D657BALL;
    if ( !v16 )
    {
      *(_QWORD *)&v25 = 655368;
      v14 = L"Appx";
      v12 = 1;
      goto LABEL_13;
    }
    v14 = L"Exe";
  }
  else
  {
    v26.MaximumLength = *(_WORD *)(a7 + 8);
    v26.Length = v26.MaximumLength;
    v26.Buffer = (PWSTR)(a7 + 10);
    v14 = L"Dll";
  }
  *(_QWORD *)&v25 = 524294;
LABEL_13:
  v17 = 0;
  for ( *((_QWORD *)&v25 + 1) = v14; v17 < a2; ++v17 )
  {
    v18 = 32LL * v17;
    if ( v22 )
    {
      v19 = *(unsigned int *)(*(_QWORD *)(v18 + a3 + 24) + 24LL);
      if ( (v19 & 0xC) == 0 )
        continue;
      v20 = v18 + a3;
    }
    else
    {
      v20 = v18 + a3;
      v19 = *(unsigned int *)(*(_QWORD *)(v18 + a3 + 24) + 24LL);
      LOBYTE(v19) = v19 & 0xC;
      if ( (_BYTE)v19 == 8 )
        continue;
    }
    AiEvaluateAppLockerPolicyClass(v19, v18, v20, a6, a9);
    SrpDisplayAccessReason(
      qword_1400196F8,
      *(_QWORD *)(v20 + 24),
      (unsigned __int16 *)&v25,
      a9[1],
      &v26,
      a6,
      (char)a5,
      v12);
    if ( *a9 )
    {
      if ( !v12 )
        break;
      if ( (unsigned __int8)AiResultIsExplicitDeny(a9) )
        break;
      v23[0] = 0;
      if ( (int)AiIsAppxInbox(a8, v23) < 0 || !v23[0] )
        break;
      *a9 = 0;
    }
  }
LABEL_25:
  if ( Handle )
    ZwClose(Handle);
  return 0;
}

```

## disassembly

```asm
0x140024280  mov     [rsp-28h+arg_0], rbx
0x140024285  mov     [rsp-28h+arg_10], rsi
0x14002428a  mov     [rsp-28h+arg_8], edx
0x14002428e  push    rbp
0x14002428f  push    rdi
0x140024290  push    r12
0x140024292  push    r13
0x140024294  push    r14
0x140024296  mov     rbp, rsp
0x140024299  sub     rsp, 70h
0x14002429d  mov     r14d, edx
0x1400242a0  mov     [rbp+Handle], 0
0x1400242a8  mov     rbx, rcx
0x1400242ab  mov     [rbp+var_30], 0
0x1400242af  mov     rcx, [rbp+arg_20]
0x1400242b3  lea     rdx, [rbp+Handle]
0x1400242b7  xorps   xmm0, xmm0
0x1400242ba  xorps   xmm1, xmm1
0x1400242bd  movups  [rbp+var_20], xmm0
0x1400242c1  mov     r13, r8
0x1400242c4  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x1400242c8  call    AiOpenTokenByProcessId
0x1400242cd  test    eax, eax
0x1400242cf  js      loc_14002445B
0x1400242d5  mov     rcx, [rbp+Handle]
0x1400242d9  lea     rdx, [rbp+var_30]
0x1400242dd  call    SrpIsTokenService
0x1400242e2  test    eax, eax
0x1400242e4  js      loc_14002445B
0x1400242ea  mov     rcx, cs:qword_14000C150
0x1400242f1  xor     r12b, r12b
0x1400242f4  sub     rcx, [rbx]
0x1400242f7  jnz     short loc_140024304
0x1400242f9  mov     rcx, cs:qword_14000C158
0x140024300  sub     rcx, [rbx+8]
0x140024304  test    rcx, rcx
0x140024307  jnz     short loc_14002432A
0x140024309  mov     rcx, [rbp+arg_30]
0x14002430d  movzx   eax, word ptr [rcx+8]
0x140024311  mov     [rbp+var_10.MaximumLength], ax
0x140024315  mov     [rbp+var_10.Length], ax
0x140024319  lea     rax, [rcx+0Ah]
0x14002431d  mov     [rbp+var_10.Buffer], rax
0x140024321  lea     rax, aDll; "Dll"
0x140024328  jmp     short loc_140024371
0x14002432a  mov     rax, [rbp+arg_30]
0x14002432e  mov     rcx, [rax+30h]
0x140024332  mov     rax, [rbx]
0x140024335  sub     rax, cs:qword_14000C160
0x14002433c  movups  xmm0, xmmword ptr [rcx]
0x14002433f  movdqu  xmmword ptr [rbp+var_10.Length], xmm0
0x140024344  jnz     short loc_140024351
0x140024346  mov     rax, [rbx+8]
0x14002434a  sub     rax, cs:qword_14000C168
0x140024351  test    rax, rax
0x140024354  jnz     short loc_14002436A
0x140024356  mov     qword ptr [rbp+var_20], 0A0008h
0x14002435e  lea     rax, aAppx; "Appx"
0x140024365  mov     r12b, 1
0x140024368  jmp     short loc_140024379
0x14002436a  lea     rax, aExe; "Exe"
0x140024371  mov     qword ptr [rbp+var_20], 80006h
0x140024379  xor     edi, edi
0x14002437b  mov     qword ptr [rbp+var_20+8], rax
0x14002437f  mov     ebx, 8
0x140024384  test    r14d, r14d
0x140024387  jz      loc_14002445B
0x14002438d  mov     r14, [rbp+arg_40]
0x140024391  mov     edx, edi
0x140024393  shl     rdx, 5
0x140024397  cmp     [rbp+var_30], 0
0x14002439b  jz      short loc_1400243B4
0x14002439d  mov     rax, [rdx+r13+18h]
0x1400243a2  mov     ecx, [rax+18h]
0x1400243a5  test    cl, 0Ch
0x1400243a8  jz      loc_140024450
0x1400243ae  cmp     [rbp+var_30], 0
0x1400243b2  jnz     short loc_1400243CC
0x1400243b4  lea     rsi, [rdx+r13]
0x1400243b8  mov     rax, [rsi+18h]
0x1400243bc  mov     ecx, [rax+18h]
0x1400243bf  and     cl, 0Ch
0x1400243c2  cmp     cl, bl
0x1400243c4  jz      loc_140024450
0x1400243ca  jmp     short loc_1400243D0
0x1400243cc  lea     rsi, [rdx+r13]
0x1400243d0  mov     r9, [rbp+arg_28]
0x1400243d4  mov     r8, rsi
0x1400243d7  mov     [rsp+70h+var_50], r14
0x1400243dc  call    AiEvaluateAppLockerPolicyClass
0x1400243e1  mov     rax, [rbp+arg_20]
0x1400243e5  lea     r8, [rbp+var_20]
0x1400243e9  mov     r9d, [r14+4]
0x1400243ed  mov     rdx, [rsi+18h]
0x1400243f1  mov     rcx, cs:qword_1400196F8; RegHandle
0x1400243f8  mov     [rsp+70h+var_38], r12b; char
0x1400243fd  mov     dword ptr [rsp+70h+var_40], eax; char
0x140024401  mov     rax, [rbp+arg_28]
0x140024405  mov     [rsp+70h+var_48], rax; HANDLE
0x14002440a  lea     rax, [rbp+var_10]
0x14002440e  mov     [rsp+70h+var_50], rax; PCUNICODE_STRING
0x140024413  call    SrpDisplayAccessReason
0x140024418  cmp     dword ptr [r14], 0
0x14002441c  jz      short loc_140024450
0x14002441e  test    r12b, r12b
0x140024421  jz      short loc_14002445B
0x140024423  mov     rcx, r14
0x140024426  call    AiResultIsExplicitDeny
0x14002442b  test    al, al
0x14002442d  jnz     short loc_14002445B
0x14002442f  mov     rcx, [rbp+arg_38]
0x140024433  lea     rdx, [rbp+var_2F]
0x140024437  mov     [rbp+var_2F], al
0x14002443a  call    AiIsAppxInbox
0x14002443f  test    eax, eax
0x140024441  js      short loc_14002445B
0x140024443  cmp     [rbp+var_2F], 0
0x140024447  jz      short loc_14002445B
0x140024449  mov     dword ptr [r14], 0
0x140024450  inc     edi
0x140024452  cmp     edi, [rbp+arg_8]
0x140024455  jb      loc_140024391
0x14002445b  mov     rcx, [rbp+Handle]; Handle
0x14002445f  test    rcx, rcx
0x140024462  jz      short loc_140024470
0x140024464  call    cs:__imp_ZwClose
0x14002446b  nop     dword ptr [rax+rax+00h]
0x140024470  lea     r11, [rsp+70h+var_s0]
0x140024475  xor     eax, eax
0x140024477  mov     rbx, [r11+30h]
0x14002447b  mov     rsi, [r11+40h]
0x14002447f  mov     rsp, r11
0x140024482  pop     r14
0x140024484  pop     r13
0x140024486  pop     r12
0x140024488  pop     rdi
0x140024489  pop     rbp
0x14002448a  retn
```
