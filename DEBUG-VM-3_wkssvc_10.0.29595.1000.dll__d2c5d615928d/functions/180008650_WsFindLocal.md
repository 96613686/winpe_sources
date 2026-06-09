# WsFindLocal

- ea: `0x180008650`
- end: `0x18000872c`
- name: `WsFindLocal`
- size: `220`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001710`
- `0x1800084d8`
- `0x1800299a4`

## callees

- `0x180008650`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x1800086fc`
- `ntdll!RtlCompareUnicodeString` at `0x1800086fc`

## pseudocode

```c
LONG __fastcall WsFindLocal(_QWORD *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *i; // rdi
  WCHAR *v8; // r10
  __int64 v9; // rax
  __int64 v10; // rax
  LONG result; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+30h] [rbp-38h] BYREF

  *a4 = a1;
  for ( i = a1; i; i = (_QWORD *)*i )
  {
    v8 = (WCHAR *)i[2];
    if ( v8 )
    {
      String1 = 0;
      v9 = -1;
      String2 = 0;
      do
        ++v9;
      while ( v8[v9] );
      String1.Buffer = v8;
      String1.MaximumLength = 2 * (v9 + 1);
      String1.Length = String1.MaximumLength;
      v10 = -1;
      do
        ++v10;
      while ( a2[v10] );
      String2.Buffer = a2;
      String2.MaximumLength = 2 * (v10 + 1);
      String2.Length = String2.MaximumLength;
      result = RtlCompareUnicodeString(&String1, &String2, 1u);
      if ( !result )
      {
        *a3 = i;
        return result;
      }
    }
    *a4 = i;
  }
  result = 0;
  *a4 = 0;
  *a3 = 0;
  return result;
}

```

## disassembly

```asm
0x180008650  push    rbx
0x180008652  push    rsi
0x180008653  push    rdi
0x180008654  push    r14
0x180008656  sub     rsp, 48h
0x18000865a  mov     rsi, r9
0x18000865d  mov     [r9], rcx
0x180008660  mov     r14, r8
0x180008663  mov     rbx, rdx
0x180008666  mov     rdi, rcx
0x180008669  nop     dword ptr [rax+00000000h]
0x180008670  test    rdi, rdi
0x180008673  jz      loc_18000871E
0x180008679  mov     r10, [rdi+10h]
0x18000867d  test    r10, r10
0x180008680  jz      loc_180008706
0x180008686  xorps   xmm0, xmm0
0x180008689  xorps   xmm1, xmm1
0x18000868c  movups  xmmword ptr [rsp+68h+String1.Length], xmm0
0x180008691  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008698  movups  xmmword ptr [rsp+68h+String2.Length], xmm1
0x18000869d  nop     dword ptr [rax]
0x1800086a0  inc     rax
0x1800086a3  cmp     word ptr [r10+rax*2], 0
0x1800086a9  jnz     short loc_1800086A0
0x1800086ab  inc     ax
0x1800086ae  mov     [rsp+68h+String1.Buffer], r10
0x1800086b3  add     ax, ax
0x1800086b6  mov     [rsp+68h+String1.MaximumLength], ax
0x1800086bb  mov     [rsp+68h+String1.Length], ax
0x1800086c0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800086c7  nop     word ptr [rax+rax+00000000h]
0x1800086d0  inc     rax
0x1800086d3  cmp     word ptr [rbx+rax*2], 0
0x1800086d8  jnz     short loc_1800086D0
0x1800086da  inc     ax
0x1800086dd  mov     [rsp+68h+String2.Buffer], rbx
0x1800086e2  add     ax, ax
0x1800086e5  lea     rdx, [rsp+68h+String2]; String2
0x1800086ea  mov     r8b, 1; CaseInsensitive
0x1800086ed  mov     [rsp+68h+String2.MaximumLength], ax
0x1800086f2  lea     rcx, [rsp+68h+String1]; String1
0x1800086f7  mov     [rsp+68h+String2.Length], ax
0x1800086fc  call    cs:__imp_RtlCompareUnicodeString
0x180008702  test    eax, eax
0x180008704  jz      short loc_180008711
0x180008706  mov     [rsi], rdi
0x180008709  mov     rdi, [rdi]
0x18000870c  jmp     loc_180008670
0x180008711  mov     [r14], rdi
0x180008714  add     rsp, 48h
0x180008718  pop     r14
0x18000871a  pop     rdi
0x18000871b  pop     rsi
0x18000871c  pop     rbx
0x18000871d  retn
0x18000871e  xor     eax, eax
0x180008720  mov     qword ptr [rsi], 0
0x180008727  mov     [r14], rax
0x18000872a  jmp     short loc_180008714
```
