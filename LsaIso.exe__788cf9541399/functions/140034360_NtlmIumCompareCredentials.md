# NtlmIumCompareCredentials

- ea: `0x140034360`
- end: `0x140034446`
- name: `NtlmIumCompareCredentials`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140034360`
- `0x140036038`
- `0x140036080`
- `0x140036330`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034380`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140034380`
- `NtlmShared!MsvpCompareCredentials` at `0x1400343e9`
- `NtlmShared!MsvpCompareCredentials` at `0x1400343e9`

## string_xrefs

- `0x14003440e`: `NtlmIumCompareCredentials`

## pseudocode

```c
__int64 __fastcall NtlmIumCompareCredentials(
        __int64 a1,
        _BYTE *a2,
        struct _MSV1_0_SECRETS_WRAPPER *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  struct _MSV1_0_SECRETS_WRAPPER *v7; // rdi
  _BYTE *v8; // rsi
  int v10; // ebx
  const char *v11; // r8
  __int64 v12; // rax
  __int64 v13; // rcx

  v7 = a3;
  v8 = a2;
  if ( qword_140052C50 == a1 )
  {
    if ( a2 && a3 )
    {
      v10 = 0;
      if ( !a2[8] || (v10 = IumpUnprotectCredential((struct _MSV1_0_SECRETS_WRAPPER *)a2), v10 >= 0) )
      {
        if ( !*((_BYTE *)v7 + 8) || (v10 = IumpUnprotectCredential(v7), v10 >= 0) )
          MsvpCompareCredentials(v8, v7, a4, a5, a6);
      }
      v12 = 352;
      v13 = 352;
      do
      {
        *v8++ = 0;
        --v13;
      }
      while ( v13 );
      do
      {
        *(_BYTE *)v7 = 0;
        v7 = (struct _MSV1_0_SECRETS_WRAPPER *)((char *)v7 + 1);
        --v12;
      }
      while ( v12 );
      if ( v10 < 0 )
        NtlmTraceErrorWithStatusViaWpp("NtlmIumCompareCredentials", 0x279u, "NtlmFailure", v10);
      else
        NtlmTraceInfoViaWpp("NtlmIumCompareCredentials", 0x279u, v11);
      return (unsigned int)v10;
    }
    else
    {
      return 3221225485LL;
    }
  }
  else
  {
    Sleep(5u);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x140034360  push    rbx
0x140034362  push    rbp
0x140034363  push    rsi
0x140034364  push    rdi
0x140034365  sub     rsp, 38h
0x140034369  cmp     cs:qword_140052C50, rcx
0x140034370  mov     rbp, r9
0x140034373  mov     rdi, r8
0x140034376  mov     rsi, rdx
0x140034379  jz      short loc_140034390
0x14003437b  mov     ecx, 5; dwMilliseconds
0x140034380  call    cs:__imp_Sleep
0x140034386  mov     eax, 0C0000022h
0x14003438b  jmp     loc_14003443D
0x140034390  test    rsi, rsi
0x140034393  jz      loc_140034438
0x140034399  test    rdi, rdi
0x14003439c  jz      loc_140034438
0x1400343a2  xor     ebx, ebx
0x1400343a4  cmp     [rdx+8], bl
0x1400343a7  jz      short loc_1400343B7
0x1400343a9  mov     rcx, rsi; struct _MSV1_0_SECRETS_WRAPPER *
0x1400343ac  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x1400343b1  mov     ebx, eax
0x1400343b3  test    eax, eax
0x1400343b5  js      short loc_1400343EF
0x1400343b7  cmp     byte ptr [rdi+8], 0
0x1400343bb  jz      short loc_1400343CB
0x1400343bd  mov     rcx, rdi; struct _MSV1_0_SECRETS_WRAPPER *
0x1400343c0  call    ?IumpUnprotectCredential@@YAJPEAU_MSV1_0_SECRETS_WRAPPER@@@Z; IumpUnprotectCredential(_MSV1_0_SECRETS_WRAPPER *)
0x1400343c5  mov     ebx, eax
0x1400343c7  test    eax, eax
0x1400343c9  js      short loc_1400343EF
0x1400343cb  mov     rax, [rsp+58h+arg_28]
0x1400343d3  mov     r8, rbp
0x1400343d6  mov     r9, [rsp+58h+arg_20]
0x1400343de  mov     rdx, rdi
0x1400343e1  mov     rcx, rsi
0x1400343e4  mov     [rsp+58h+var_38], rax
0x1400343e9  call    cs:__imp_MsvpCompareCredentials
0x1400343ef  mov     eax, 160h
0x1400343f4  mov     ecx, eax
0x1400343f6  mov     byte ptr [rsi], 0
0x1400343f9  inc     rsi
0x1400343fc  sub     rcx, 1
0x140034400  jnz     short loc_1400343F6
0x140034402  mov     byte ptr [rdi], 0
0x140034405  inc     rdi
0x140034408  sub     rax, 1
0x14003440c  jnz     short loc_140034402
0x14003440e  lea     rcx, aNtlmiumcompare_0; "NtlmIumCompareCredentials"
0x140034415  mov     edx, 279h; unsigned int
0x14003441a  test    ebx, ebx
0x14003441c  js      short loc_140034425
0x14003441e  call    ?NtlmTraceInfoViaWpp@@YAXPEBDK0@Z; NtlmTraceInfoViaWpp(char const *,ulong,char const *)
0x140034423  jmp     short loc_140034434
0x140034425  mov     r9d, ebx; int
0x140034428  lea     r8, aNtlmfailure; "NtlmFailure"
0x14003442f  call    ?NtlmTraceErrorWithStatusViaWpp@@YAXPEBDK0J@Z; NtlmTraceErrorWithStatusViaWpp(char const *,ulong,char const *,long)
0x140034434  mov     eax, ebx
0x140034436  jmp     short loc_14003443D
0x140034438  mov     eax, 0C000000Dh
0x14003443d  add     rsp, 38h
0x140034441  pop     rdi
0x140034442  pop     rsi
0x140034443  pop     rbp
0x140034444  pop     rbx
0x140034445  retn
```
