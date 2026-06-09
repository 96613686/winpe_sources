# SmartlockerTagProcessToken

- ea: `0x140023110`
- end: `0x140023183`
- name: `SmartlockerTagProcessToken`
- size: `115`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140022d58`
- `0x1400236ac`
- `0x14002f560`
- `0x140030ab0`
- `0x140030c80`
- `0x1400315b0`
- `0x140032fc0`

## import_xrefs

- `ntoskrnl!SeSetSecurityAttributesToken` at `0x140023170`
- `ntoskrnl!SeSetSecurityAttributesToken` at `0x140023170`

## pseudocode

```c
__int64 __fastcall SmartlockerTagProcessToken(__int64 a1, int a2, __int64 a3)
{
  _DWORD v4[2]; // [rsp+20h] [rbp-50h] BYREF
  __int128 *v5; // [rsp+28h] [rbp-48h]
  __int64 v6; // [rsp+30h] [rbp-40h] BYREF
  int v7; // [rsp+38h] [rbp-38h]
  int v8; // [rsp+3Ch] [rbp-34h]
  __int128 v9; // [rsp+40h] [rbp-30h] BYREF
  int v10; // [rsp+50h] [rbp-20h]
  int v11; // [rsp+54h] [rbp-1Ch]
  int v12; // [rsp+58h] [rbp-18h]
  __int64 *v13; // [rsp+60h] [rbp-10h]
  int v14; // [rsp+88h] [rbp+18h] BYREF

  v7 = a2;
  v5 = &v9;
  v4[0] = 1;
  v4[1] = 1;
  v12 = 1;
  v6 = a3;
  v13 = &v6;
  v8 = 0;
  v9 = *(_OWORD *)L"24";
  v10 = 16;
  v11 = 66;
  v14 = 4;
  return ((__int64 (__fastcall *)(__int64, _QWORD, int *, _DWORD *))SeSetSecurityAttributesToken)(a1, 0, &v14, v4);
}

```

## disassembly

```asm
0x140023110  push    rbp
0x140023112  mov     rbp, rsp
0x140023115  sub     rsp, 70h
0x140023119  movups  xmm0, xmmword ptr cs:a24_0; "24"
0x140023120  mov     [rbp+var_38], edx
0x140023123  lea     rax, [rbp+var_30]
0x140023127  mov     edx, 1
0x14002312c  mov     [rbp+var_48], rax
0x140023130  mov     [rbp+var_50], edx
0x140023133  lea     rax, [rbp+var_40]
0x140023137  mov     [rbp+var_4C], edx
0x14002313a  lea     r9, [rbp+var_50]
0x14002313e  mov     [rbp+var_18], edx
0x140023141  xor     edx, edx
0x140023143  mov     [rbp+var_40], r8
0x140023147  lea     r8, [rbp+arg_8]
0x14002314b  mov     [rbp+var_10], rax
0x14002314f  mov     [rbp+var_34], 0
0x140023156  movdqu  [rbp+var_30], xmm0
0x14002315b  mov     [rbp+var_20], 10h
0x140023162  mov     [rbp+var_1C], 42h ; 'B'
0x140023169  mov     [rbp+arg_8], 4
0x140023170  call    cs:__imp_SeSetSecurityAttributesToken
0x140023177  nop     dword ptr [rax+rax+00h]
0x14002317c  add     rsp, 70h
0x140023180  pop     rbp
0x140023181  retn
```
