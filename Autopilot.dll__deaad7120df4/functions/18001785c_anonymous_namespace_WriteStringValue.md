# _anonymous_namespace_::WriteStringValue

- ea: `0x18001785c`
- end: `0x180017926`
- name: `_anonymous_namespace_::WriteStringValue`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015f48`

## callees

- `0x180010764`
- `0x180016b80`
- `0x18001785c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800178cb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800178cb`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::WriteStringValue(HKEY *a1, const WCHAR *a2, const BYTE *lpData)
{
  __int64 v3; // r10
  const BYTE *v4; // rax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !lpData )
  {
    v5 = -2147024809;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
      (const char *)v5);
    return v5;
  }
  v3 = 0x7FFFFFFF;
  v4 = lpData;
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
  v6 = RegSetValueExW(*a1, a2, 0, 1u, lpData, v3 != 0 ? -2 - 2 * v3 + 2 : 2);
  if ( v6 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x44,
             (int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
             (const char *)v6);
  else
    return 0;
}

```

## disassembly

```asm
0x18001785c  mov     [rsp+arg_0], rbx
0x180017861  push    rdi
0x180017862  sub     rsp, 30h
0x180017866  xor     edi, edi
0x180017868  mov     r11, rcx
0x18001786b  test    r8, r8
0x18001786e  jz      loc_1800178FA
0x180017874  mov     r10d, 7FFFFFFFh
0x18001787a  mov     rax, r8
0x18001787d  cmp     [rax], di
0x180017880  jz      short loc_18001788C
0x180017882  add     rax, 2
0x180017886  sub     r10, 1
0x18001788a  jnz     short loc_18001787D
0x18001788c  mov     rax, r10
0x18001788f  neg     rax
0x180017892  sbb     ebx, ebx
0x180017894  not     ebx
0x180017896  and     ebx, 80070057h
0x18001789c  test    r10, r10
0x18001789f  jz      short loc_1800178FF
0x1800178a1  lea     eax, [r10+r10]
0x1800178a5  mov     ecx, 0FFFFFFFEh
0x1800178aa  sub     ecx, eax
0x1800178ac  mov     r9d, 1; dwType
0x1800178b2  neg     r10
0x1800178b5  sbb     eax, eax
0x1800178b7  and     eax, ecx
0x1800178b9  mov     rcx, [r11]; hKey
0x1800178bc  add     eax, 2
0x1800178bf  mov     [rsp+38h+cbData], eax; cbData
0x1800178c3  mov     [rsp+38h+lpData], r8; unsigned int
0x1800178c8  xor     r8d, r8d; Reserved
0x1800178cb  call    cs:__imp_RegSetValueExW
0x1800178d2  nop     dword ptr [rax+rax+00h]
0x1800178d7  test    eax, eax
0x1800178d9  jz      short loc_1800178F6
0x1800178db  mov     rcx, [rsp+38h]; this
0x1800178e0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800178e7  mov     r9d, eax; char *
0x1800178ea  mov     edx, 44h ; 'D'; void *
0x1800178ef  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800178f4  jmp     short loc_18001791A
0x1800178f6  xor     eax, eax
0x1800178f8  jmp     short loc_18001791A
0x1800178fa  mov     ebx, 80070057h
0x1800178ff  mov     rcx, [rsp+38h]; this
0x180017904  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001790b  mov     r9d, ebx; char *
0x18001790e  mov     edx, 3Ah ; ':'; void *
0x180017913  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017918  mov     eax, ebx
0x18001791a  mov     rbx, [rsp+38h+arg_0]
0x18001791f  add     rsp, 30h
0x180017923  pop     rdi
0x180017924  retn
```
