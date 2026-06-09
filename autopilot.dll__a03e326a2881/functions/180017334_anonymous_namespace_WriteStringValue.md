# _anonymous_namespace_::WriteStringValue

- ea: `0x180017334`
- end: `0x1800173f7`
- name: `_anonymous_namespace_::WriteStringValue`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015af0`

## callees

- `0x1800105f4`
- `0x1800166dc`
- `0x180017334`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800173a3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800173a3`

## pseudocode

```c
int __fastcall anonymous_namespace_::WriteStringValue(HKEY *a1, const WCHAR *a2, const BYTE *a3)
{
  __int64 v3; // r10
  const BYTE *v4; // rax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  int lpData; // [rsp+20h] [rbp-18h]
  unsigned int lpDataa; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !a3 )
  {
    v5 = -2147024809;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
      (const char *)v5,
      lpData);
    return v5;
  }
  v3 = 0x7FFFFFFF;
  v4 = a3;
  do
  {
    if ( !*(_WORD *)v4 )
      break;
    v4 += 2;
    --v3;
  }
  while ( v3 );
  v5 = v3 == 0 ? 0x80070057 : 0;
  if ( !v3 )
    goto LABEL_10;
  v6 = RegSetValueExW(*a1, a2, 0, 1u, a3, v3 != 0 ? -2 - 2 * v3 + 2 : 2);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x44,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
             (const char *)v6,
             lpDataa);
  else
    return 0;
}

```

## disassembly

```asm
0x180017334  mov     [rsp+arg_0], rbx
0x180017339  push    rdi
0x18001733a  sub     rsp, 30h
0x18001733e  xor     edi, edi
0x180017340  mov     r11, rcx
0x180017343  test    r8, r8
0x180017346  jz      loc_1800173CC
0x18001734c  mov     r10d, 7FFFFFFFh
0x180017352  mov     rax, r8
0x180017355  cmp     [rax], di
0x180017358  jz      short loc_180017364
0x18001735a  add     rax, 2
0x18001735e  sub     r10, 1
0x180017362  jnz     short loc_180017355
0x180017364  mov     rax, r10
0x180017367  neg     rax
0x18001736a  sbb     ebx, ebx
0x18001736c  not     ebx
0x18001736e  and     ebx, 80070057h
0x180017374  test    r10, r10
0x180017377  jz      short loc_1800173D1
0x180017379  lea     eax, [r10+r10]
0x18001737d  mov     ecx, 0FFFFFFFEh
0x180017382  sub     ecx, eax
0x180017384  mov     r9d, 1; dwType
0x18001738a  neg     r10
0x18001738d  sbb     eax, eax
0x18001738f  and     eax, ecx
0x180017391  mov     rcx, [r11]; hKey
0x180017394  add     eax, 2
0x180017397  mov     [rsp+38h+cbData], eax; cbData
0x18001739b  mov     [rsp+38h+lpData], r8; unsigned int
0x1800173a0  xor     r8d, r8d; Reserved
0x1800173a3  call    cs:__imp_RegSetValueExW
0x1800173a9  test    eax, eax
0x1800173ab  jz      short loc_1800173C8
0x1800173ad  mov     rcx, [rsp+38h]; this
0x1800173b2  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800173b9  mov     r9d, eax; char *
0x1800173bc  mov     edx, 44h ; 'D'; void *
0x1800173c1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800173c6  jmp     short loc_1800173EC
0x1800173c8  xor     eax, eax
0x1800173ca  jmp     short loc_1800173EC
0x1800173cc  mov     ebx, 80070057h
0x1800173d1  mov     rcx, [rsp+38h]; this
0x1800173d6  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800173dd  mov     r9d, ebx; char *
0x1800173e0  mov     edx, 3Ah ; ':'; void *
0x1800173e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800173ea  mov     eax, ebx
0x1800173ec  mov     rbx, [rsp+38h+arg_0]
0x1800173f1  add     rsp, 30h
0x1800173f5  pop     rdi
0x1800173f6  retn
```
