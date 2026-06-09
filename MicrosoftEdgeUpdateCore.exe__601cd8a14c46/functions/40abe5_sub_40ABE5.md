# sub_40ABE5

- ea: `0x40abe5`
- end: `0x40ac88`
- name: `sub_40ABE5`
- size: `163`
- prototype: `int __thiscall(_DWORD *this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x40bca4`

## callees

- `0x4015d2`
- `0x401cfa`
- `0x404564`
- `0x405ba1`
- `0x4071af`
- `0x40abe5`

## string_xrefs

- `0x40ac4a`: `[allow_installation][%d]`

## pseudocode

```c
int __thiscall sub_40ABE5(_DWORD *this, unsigned __int8 *a2)
{
  int result; // eax
  int v4; // ecx
  int v5[4]; // [esp+Ch] [ebp-18h] BYREF
  _DWORD v6[2]; // [esp+1Ch] [ebp-8h] BYREF

  if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
  {
    v5[0] = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
    v5[1] = 7;
    v5[2] = 1;
    v6[0] = 0;
    v5[3] = sub_4071AF(v5[0], 7, 1);
    sub_401CFA(v6, (wchar_t *)aC_1);
    sub_405BA1((int)v6, (int)L"[is_managed][%d]", *a2);
    sub_405BA1((int)v6, (int)L"[allow_installation][%d]", *((_DWORD *)a2 + 1));
    sub_404564(v5, (int)&off_439EE8, v6[0]);
    sub_4015D2((volatile signed __int32 *)(v6[0] - 16));
  }
  result = *(_DWORD *)a2;
  v4 = *((_DWORD *)a2 + 1);
  this[1] = *(_DWORD *)a2;
  this[2] = v4;
  return result;
}

```

## disassembly

```asm
0x40abe5  push    ebp
0x40abe6  mov     ebp, esp
0x40abe8  sub     esp, 1Ch
0x40abeb  push    esi
0x40abec  mov     esi, [ebp+arg_0]
0x40abef  push    edi
0x40abf0  mov     edi, ecx
0x40abf2  movzx   ecx, byte_43EE81
0x40abf9  neg     ecx
0x40abfb  sbb     ecx, ecx
0x40abfd  and     ecx, offset dword_43ED80
0x40ac03  jz      short loc_40AC77
0x40ac05  push    7
0x40ac07  pop     edx
0x40ac08  xor     eax, eax
0x40ac0a  mov     [ebp+var_18], ecx
0x40ac0d  inc     eax
0x40ac0e  mov     [ebp+var_14], edx
0x40ac11  push    eax
0x40ac12  push    edx
0x40ac13  mov     [ebp+var_10], eax
0x40ac16  call    sub_4071AF
0x40ac1b  and     [ebp+var_8], 0
0x40ac1f  lea     ecx, [ebp+var_8]
0x40ac22  push    offset aC_1; String
0x40ac27  mov     [ebp+var_C], eax
0x40ac2a  call    sub_401CFA
0x40ac2f  movzx   eax, byte ptr [esi]
0x40ac32  push    eax
0x40ac33  lea     eax, [ebp+var_8]
0x40ac36  push    offset aIsManagedD; "[is_managed][%d]"
0x40ac3b  push    eax
0x40ac3c  call    sub_405BA1
0x40ac41  add     esp, 0Ch
0x40ac44  lea     eax, [ebp+var_8]
0x40ac47  push    dword ptr [esi+4]
0x40ac4a  push    offset aAllowInstallat; "[allow_installation][%d]"
0x40ac4f  push    eax
0x40ac50  call    sub_405BA1
0x40ac55  add     esp, 0Ch
0x40ac58  lea     eax, [ebp+var_18]
0x40ac5b  push    [ebp+var_8]
0x40ac5e  push    offset off_439EE8; "䐀䔀㌀䈀㘀䔀㔀ⴀ\u3100䘀㘀㌀ⴀ㐀䘀㈀䐀ⴀ㠀䌀㠀䔀ⴀ㠀䄀㘀䐀\u3100䘀"...
0x40ac63  push    eax
0x40ac64  call    sub_404564
0x40ac69  mov     ecx, [ebp+var_8]
0x40ac6c  add     esp, 0Ch
0x40ac6f  lea     ecx, [ecx-10h]
0x40ac72  call    sub_4015D2
0x40ac77  mov     eax, [esi]
0x40ac79  mov     ecx, [esi+4]
0x40ac7c  mov     [edi+4], eax
0x40ac7f  mov     [edi+8], ecx
0x40ac82  pop     edi
0x40ac83  pop     esi
0x40ac84  leave
0x40ac85  retn    4
```
