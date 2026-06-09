# MpGetKnownProcessType

- ea: `0x140037e78`
- end: `0x14003836f`
- name: `MpGetKnownProcessType`
- size: `1271`
- prototype: `__int64 __fastcall(PUNICODE_STRING Name)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400387f0`
- `0x14006eba0`

## callees

- `0x14000a364`
- `0x140037e78`
- `0x140038370`

## import_xrefs

- `ntoskrnl!FsRtlIsNameInExpression` at `0x140038171`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140038260`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14003828f`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140038171`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x140038260`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14003828f`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400380f1`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140038196`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x1400380f1`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140038196`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140037ed7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140037ed7`

## pseudocode

```c
__int64 __fastcall MpGetKnownProcessType(PUNICODE_STRING Name, _DWORD *a2)
{
  const UNICODE_STRING **v4; // r14
  unsigned int i; // esi
  const UNICODE_STRING *v6; // rdx
  const UNICODE_STRING *v7; // rcx
  const UNICODE_STRING *v8; // rcx

  if ( Name && a2 )
  {
    *a2 = 0;
    v4 = (const UNICODE_STRING **)&qword_140026420;
    for ( i = 0; i < 0xC; ++i )
    {
      v6 = *v4;
      if ( *v4 && v6->Length == Name->Length && !RtlCompareUnicodeString(Name, v6, 1u) )
      {
        *a2 = qword_140026410[3 * (int)i];
        return 0;
      }
      v4 += 3;
    }
    if ( *(int *)(MpData + 868) < 0 )
    {
      if ( (unsigned __int8)MpSuffixUnicodeString(&qword_14001EAF8, Name) )
      {
        *a2 = 24;
        return 0;
      }
      if ( (unsigned __int8)MpSuffixUnicodeString(&qword_14001EAE8, Name) )
      {
        *a2 = 25;
        return 0;
      }
    }
    v7 = *(const UNICODE_STRING **)(MpData + 3264);
    if ( v7 && RtlPrefixUnicodeString(v7, Name, 1u) )
    {
      if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013248, Name)
        && Name->Length == **(unsigned __int16 **)(MpData + 3264) + 140
        || (unsigned __int8)MpSuffixUnicodeString(&qword_140013228, Name)
        && FsRtlIsNameInExpression(&stru_140026400, Name, 1u, 0) )
      {
        *a2 = 7;
        return 0;
      }
      if ( (unsigned __int8)MpSuffixUnicodeString(L",.", Name) && FsRtlIsNameInExpression(&stru_1400263E0, Name, 1u, 0) )
      {
        *a2 = 23;
        return 0;
      }
      if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013218, Name)
        && FsRtlIsNameInExpression(&Expression, Name, 1u, 0) )
      {
        *a2 = 18;
        return 0;
      }
    }
    v8 = *(const UNICODE_STRING **)(MpData + 3936);
    if ( v8 && RtlPrefixUnicodeString(v8, Name, 1u) && (unsigned __int8)MpSuffixUnicodeString(&qword_14001EB18, Name) )
    {
      *a2 = 8;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140012D38, Name) )
    {
      *a2 = 4;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013050, Name) )
    {
      *a2 = 5;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013030, Name) )
    {
      *a2 = 6;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013080, Name)
      || (unsigned __int8)MpSuffixUnicodeString(L"&(", Name) )
    {
      *a2 = 9;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013090, Name) )
    {
      *a2 = 10;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_1400130A0, Name) )
    {
      *a2 = 12;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013070, Name) )
    {
      *a2 = 11;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013060, Name) )
    {
      *a2 = 13;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_140013130, Name) )
    {
      *a2 = 14;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_1400131B8, Name)
      || (unsigned __int8)MpSuffixUnicodeString(L"\"$", Name) )
    {
      *a2 = 15;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_1400131D8, Name) )
    {
      *a2 = 27;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(L".0", Name) )
    {
      *a2 = 35;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(&qword_1400131E8, Name)
      || (unsigned __int8)MpSuffixUnicodeString(&qword_140013208, Name) )
    {
      *a2 = 28;
      return 0;
    }
    if ( (unsigned __int8)MpSuffixUnicodeString(L"$&", Name) )
    {
      *a2 = 32;
      return 0;
    }
    return 3221226021LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        62,
        (unsigned int)WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids,
        (unsigned int)KeGetCurrentThread(),
        (__int64)Name,
        (__int64)a2);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140037e78  mov     [rsp+arg_0], rbx
0x140037e7d  mov     [rsp+arg_8], rsi
0x140037e82  mov     [rsp+arg_10], rdi
0x140037e87  push    r14
0x140037e89  sub     rsp, 30h
0x140037e8d  mov     rbx, rdx
0x140037e90  mov     rdi, rcx
0x140037e93  test    rcx, rcx
0x140037e96  jz      loc_14003831C
0x140037e9c  test    rdx, rdx
0x140037e9f  jz      loc_14003831C
0x140037ea5  mov     dword ptr [rdx], 0
0x140037eab  lea     r14, qword_140026420
0x140037eb2  xor     esi, esi
0x140037eb4  cmp     esi, 0Ch
0x140037eb7  jnb     short loc_140037EFC
0x140037eb9  mov     rdx, [r14]; String2
0x140037ebc  test    rdx, rdx
0x140037ebf  jz      short loc_140037EC9
0x140037ec1  movzx   eax, word ptr [rdi]
0x140037ec4  cmp     [rdx], ax
0x140037ec7  jz      short loc_140037ED1
0x140037ec9  inc     esi
0x140037ecb  add     r14, 18h
0x140037ecf  jmp     short loc_140037EB4
0x140037ed1  mov     r8b, 1; CaseInSensitive
0x140037ed4  mov     rcx, rdi; String1
0x140037ed7  call    cs:__imp_RtlCompareUnicodeString
0x140037ede  nop     dword ptr [rax+rax+00h]
0x140037ee3  test    eax, eax
0x140037ee5  jnz     short loc_140037EC9
0x140037ee7  movsxd  rax, esi
0x140037eea  lea     rcx, qword_140026410
0x140037ef1  lea     rax, [rax+rax*2]
0x140037ef5  mov     eax, [rcx+rax*8]
0x140037ef8  mov     [rbx], eax
0x140037efa  jmp     short loc_140037F58
0x140037efc  mov     rax, cs:MpData
0x140037f03  mov     ecx, [rax+364h]
0x140037f09  test    ecx, ecx
0x140037f0b  js      loc_1400381ED
0x140037f11  mov     rax, cs:MpData
0x140037f18  mov     rcx, [rax+0CC0h]; String1
0x140037f1f  test    rcx, rcx
0x140037f22  jnz     loc_1400380EB
0x140037f28  mov     rax, cs:MpData
0x140037f2f  mov     rcx, [rax+0F60h]; String1
0x140037f36  test    rcx, rcx
0x140037f39  jnz     loc_140038190
0x140037f3f  mov     rdx, rdi
0x140037f42  lea     rcx, qword_140012D38
0x140037f49  call    MpSuffixUnicodeString
0x140037f4e  test    al, al
0x140037f50  jz      short loc_140037F71
0x140037f52  mov     dword ptr [rbx], 4
0x140037f58  xor     eax, eax
0x140037f5a  mov     rbx, [rsp+38h+arg_0]
0x140037f5f  mov     rsi, [rsp+38h+arg_8]
0x140037f64  mov     rdi, [rsp+38h+arg_10]
0x140037f69  add     rsp, 30h
0x140037f6d  pop     r14
0x140037f6f  retn
0x140037f71  mov     rdx, rdi
0x140037f74  lea     rcx, qword_140013050
0x140037f7b  call    MpSuffixUnicodeString
0x140037f80  test    al, al
0x140037f82  jnz     loc_1400382AE
0x140037f88  mov     rdx, rdi
0x140037f8b  lea     rcx, qword_140013030
0x140037f92  call    MpSuffixUnicodeString
0x140037f97  test    al, al
0x140037f99  jnz     loc_1400382B9
0x140037f9f  mov     rdx, rdi
0x140037fa2  lea     rcx, qword_140013080
0x140037fa9  call    MpSuffixUnicodeString
0x140037fae  test    al, al
0x140037fb0  jnz     loc_140038311
0x140037fb6  mov     rdx, rdi
0x140037fb9  lea     rcx, asc_140013040; "&("
0x140037fc0  call    MpSuffixUnicodeString
0x140037fc5  test    al, al
0x140037fc7  jnz     loc_140038311
0x140037fcd  mov     rdx, rdi
0x140037fd0  lea     rcx, qword_140013090
0x140037fd7  call    MpSuffixUnicodeString
0x140037fdc  test    al, al
0x140037fde  jnz     loc_1400382C4
0x140037fe4  mov     rdx, rdi
0x140037fe7  lea     rcx, qword_1400130A0
0x140037fee  call    MpSuffixUnicodeString
0x140037ff3  test    al, al
0x140037ff5  jnz     loc_1400382CF
0x140037ffb  mov     rdx, rdi
0x140037ffe  lea     rcx, qword_140013070
0x140038005  call    MpSuffixUnicodeString
0x14003800a  test    al, al
0x14003800c  jnz     loc_1400382DA
0x140038012  mov     rdx, rdi
0x140038015  lea     rcx, qword_140013060
0x14003801c  call    MpSuffixUnicodeString
0x140038021  test    al, al
0x140038023  jnz     loc_1400381CC
0x140038029  mov     rdx, rdi
0x14003802c  lea     rcx, qword_140013130
0x140038033  call    MpSuffixUnicodeString
0x140038038  test    al, al
0x14003803a  jnz     loc_1400381D7
0x140038040  mov     rdx, rdi
0x140038043  lea     rcx, qword_1400131B8
0x14003804a  call    MpSuffixUnicodeString
0x14003804f  test    al, al
0x140038051  jnz     loc_140038306
0x140038057  mov     rdx, rdi
0x14003805a  lea     rcx, asc_1400131A8; "\"$"
0x140038061  call    MpSuffixUnicodeString
0x140038066  test    al, al
0x140038068  jnz     loc_140038306
0x14003806e  mov     rdx, rdi
0x140038071  lea     rcx, qword_1400131D8
0x140038078  call    MpSuffixUnicodeString
0x14003807d  test    al, al
0x14003807f  jnz     loc_1400382E5
0x140038085  mov     rdx, rdi
0x140038088  lea     rcx, a0; ".0"
0x14003808f  call    MpSuffixUnicodeString
0x140038094  test    al, al
0x140038096  jnz     loc_1400382F0
0x14003809c  mov     rdx, rdi
0x14003809f  lea     rcx, qword_1400131E8
0x1400380a6  call    MpSuffixUnicodeString
0x1400380ab  test    al, al
0x1400380ad  jnz     loc_1400382FB
0x1400380b3  mov     rdx, rdi
0x1400380b6  lea     rcx, qword_140013208
0x1400380bd  call    MpSuffixUnicodeString
0x1400380c2  test    al, al
0x1400380c4  jnz     loc_1400382FB
0x1400380ca  mov     rdx, rdi
0x1400380cd  lea     rcx, asc_1400131C8; "$&"
0x1400380d4  call    MpSuffixUnicodeString
0x1400380d9  test    al, al
0x1400380db  jnz     loc_1400381E2
0x1400380e1  mov     eax, 0C0000225h
0x1400380e6  jmp     loc_140037F5A
0x1400380eb  mov     r8b, 1; CaseInSensitive
0x1400380ee  mov     rdx, rdi; String2
0x1400380f1  call    cs:__imp_RtlPrefixUnicodeString
0x1400380f8  nop     dword ptr [rax+rax+00h]
0x1400380fd  test    al, al
0x1400380ff  jz      loc_140037F28
0x140038105  mov     rdx, rdi
0x140038108  lea     rcx, qword_140013248
0x14003810f  call    MpSuffixUnicodeString
0x140038114  test    al, al
0x140038116  jnz     loc_14003822D
0x14003811c  mov     rdx, rdi
0x14003811f  lea     rcx, qword_140013228
0x140038126  call    MpSuffixUnicodeString
0x14003812b  test    al, al
0x14003812d  jnz     loc_140038250
0x140038133  mov     rdx, rdi
0x140038136  lea     rcx, asc_140013238; ",."
0x14003813d  call    MpSuffixUnicodeString
0x140038142  test    al, al
0x140038144  jnz     loc_14003827F
0x14003814a  mov     rdx, rdi
0x14003814d  lea     rcx, qword_140013218
0x140038154  call    MpSuffixUnicodeString
0x140038159  test    al, al
0x14003815b  jz      loc_140037F28
0x140038161  xor     r9d, r9d; UpcaseTable
0x140038164  lea     rcx, Expression; Expression
0x14003816b  mov     r8b, 1; IgnoreCase
0x14003816e  mov     rdx, rdi; Name
0x140038171  call    cs:__imp_FsRtlIsNameInExpression
0x140038178  nop     dword ptr [rax+rax+00h]
0x14003817d  test    al, al
0x14003817f  jz      loc_140037F28
0x140038185  mov     dword ptr [rbx], 12h
0x14003818b  jmp     loc_140037F58
0x140038190  mov     r8b, 1; CaseInSensitive
0x140038193  mov     rdx, rdi; String2
0x140038196  call    cs:__imp_RtlPrefixUnicodeString
0x14003819d  nop     dword ptr [rax+rax+00h]
0x1400381a2  test    al, al
0x1400381a4  jz      loc_140037F3F
0x1400381aa  mov     rdx, rdi
0x1400381ad  lea     rcx, qword_14001EB18
0x1400381b4  call    MpSuffixUnicodeString
0x1400381b9  test    al, al
0x1400381bb  jz      loc_140037F3F
0x1400381c1  mov     dword ptr [rbx], 8
0x1400381c7  jmp     loc_140037F58
0x1400381cc  mov     dword ptr [rbx], 0Dh
0x1400381d2  jmp     loc_140037F58
0x1400381d7  mov     dword ptr [rbx], 0Eh
0x1400381dd  jmp     loc_140037F58
0x1400381e2  mov     dword ptr [rbx], 20h ; ' '
0x1400381e8  jmp     loc_140037F58
0x1400381ed  mov     rdx, rdi
0x1400381f0  lea     rcx, qword_14001EAF8
0x1400381f7  call    MpSuffixUnicodeString
0x1400381fc  test    al, al
0x1400381fe  jz      short loc_14003820B
0x140038200  mov     dword ptr [rbx], 18h
0x140038206  jmp     loc_140037F58
0x14003820b  mov     rdx, rdi
0x14003820e  lea     rcx, qword_14001EAE8
0x140038215  call    MpSuffixUnicodeString
0x14003821a  test    al, al
0x14003821c  jz      loc_140037F11
0x140038222  mov     dword ptr [rbx], 19h
0x140038228  jmp     loc_140037F58
0x14003822d  mov     rax, cs:MpData
0x140038234  mov     rcx, [rax+0CC0h]
0x14003823b  movzx   eax, word ptr [rdi]
0x14003823e  movzx   edx, word ptr [rcx]
0x140038241  add     edx, 8Ch
0x140038247  cmp     eax, edx
0x140038249  jz      short loc_140038274
0x14003824b  jmp     loc_14003811C
0x140038250  xor     r9d, r9d; UpcaseTable
0x140038253  lea     rcx, stru_140026400; Expression
0x14003825a  mov     r8b, 1; IgnoreCase
0x14003825d  mov     rdx, rdi; Name
0x140038260  call    cs:__imp_FsRtlIsNameInExpression
0x140038267  nop     dword ptr [rax+rax+00h]
0x14003826c  test    al, al
0x14003826e  jz      loc_140038133
0x140038274  mov     dword ptr [rbx], 7
0x14003827a  jmp     loc_140037F58
0x14003827f  xor     r9d, r9d; UpcaseTable
0x140038282  lea     rcx, stru_1400263E0; Expression
0x140038289  mov     r8b, 1; IgnoreCase
0x14003828c  mov     rdx, rdi; Name
0x14003828f  call    cs:__imp_FsRtlIsNameInExpression
0x140038296  nop     dword ptr [rax+rax+00h]
0x14003829b  test    al, al
0x14003829d  jz      loc_14003814A
0x1400382a3  mov     dword ptr [rbx], 17h
0x1400382a9  jmp     loc_140037F58
0x1400382ae  mov     dword ptr [rbx], 5
0x1400382b4  jmp     loc_140037F58
0x1400382b9  mov     dword ptr [rbx], 6
0x1400382bf  jmp     loc_140037F58
0x1400382c4  mov     dword ptr [rbx], 0Ah
0x1400382ca  jmp     loc_140037F58
0x1400382cf  mov     dword ptr [rbx], 0Ch
0x1400382d5  jmp     loc_140037F58
0x1400382da  mov     dword ptr [rbx], 0Bh
0x1400382e0  jmp     loc_140037F58
0x1400382e5  mov     dword ptr [rbx], 1Bh
0x1400382eb  jmp     loc_140037F58
0x1400382f0  mov     dword ptr [rbx], 23h ; '#'
0x1400382f6  jmp     loc_140037F58
0x1400382fb  mov     dword ptr [rbx], 1Ch
0x140038301  jmp     loc_140037F58
0x140038306  mov     dword ptr [rbx], 0Fh
0x14003830c  jmp     loc_140037F58
0x140038311  mov     dword ptr [rbx], 9
0x140038317  jmp     loc_140037F58
0x14003831c  mov     rax, cs:WPP_GLOBAL_Control
0x140038323  lea     rcx, WPP_GLOBAL_Control
0x14003832a  cmp     rax, rcx
0x14003832d  jz      short loc_140038365
0x14003832f  mov     eax, [rax+2Ch]
0x140038332  test    al, 2
0x140038334  jz      short loc_140038365
0x140038336  mov     r9, gs:188h
0x14003833f  lea     r8, WPP_9c9a40995a6d306ff00b675dc6e33d78_Traceguids
0x140038346  mov     rcx, cs:WPP_GLOBAL_Control
0x14003834d  mov     edx, 3Eh ; '>'
0x140038352  mov     [rsp+38h+var_10], rbx
0x140038357  mov     [rsp+38h+var_18], rdi
0x14003835c  mov     rcx, [rcx+18h]
0x140038360  call    WPP_SF_qqq
0x140038365  mov     eax, 0C000000Dh
0x14003836a  jmp     loc_140037F5A
```
