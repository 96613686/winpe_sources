# sub_40ADB0

- ea: `0x40adb0`
- end: `0x40ae67`
- name: `sub_40ADB0`
- size: `183`
- prototype: `int __thiscall(_DWORD *this, _DWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x4015d2`
- `0x402330`
- `0x404564`
- `0x4071af`
- `0x40adb0`

## string_xrefs

- `0x40ae43`: `[GetUpdatesSuppressedTimes][%s][Missing time]`

## pseudocode

```c
int __thiscall sub_40ADB0(_DWORD *this, _DWORD *a2)
{
  _DWORD *v4; // eax
  int v5[4]; // [esp+4h] [ebp-14h] BYREF
  int v6; // [esp+14h] [ebp-4h] BYREF

  if ( *((_BYTE *)this + 9) )
  {
    if ( (this[13] & this[12]) != -1 && (this[15] & this[14]) != -1 && (this[17] & this[16]) != -1 )
    {
      *a2 = this[12];
      a2[1] = this[14];
      a2[2] = this[16];
      return 0;
    }
    if ( (byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0) != 0 )
    {
      v5[0] = byte_43EE81 != 0 ? (unsigned int)dword_43ED80 : 0;
      v5[1] = 7;
      v5[2] = 5;
      v5[3] = sub_4071AF(v5[0], 7, 5);
      v4 = (_DWORD *)(*(int (__thiscall **)(_DWORD *, int *))(*this + 4))(this, &v6);
      sub_404564(v5, (int)L"[GetUpdatesSuppressedTimes][%s][Missing time]", *v4);
      sub_4015D2((volatile signed __int32 *)(v6 - 16));
    }
  }
  return -2147467259;
}

```

## disassembly

```asm
0x40adb0  push    ebp
0x40adb1  mov     ebp, esp
0x40adb3  sub     esp, 14h
0x40adb6  push    edi
0x40adb7  mov     edi, ecx
0x40adb9  cmp     byte ptr [edi+9], 0
0x40adbd  jz      loc_40AE5D
0x40adc3  mov     eax, [edi+30h]
0x40adc6  and     eax, [edi+34h]
0x40adc9  cmp     eax, 0FFFFFFFFh
0x40adcc  jz      short loc_40ADFC
0x40adce  mov     eax, [edi+38h]
0x40add1  and     eax, [edi+3Ch]
0x40add4  cmp     eax, 0FFFFFFFFh
0x40add7  jz      short loc_40ADFC
0x40add9  mov     eax, [edi+40h]
0x40addc  and     eax, [edi+44h]
0x40addf  cmp     eax, 0FFFFFFFFh
0x40ade2  jz      short loc_40ADFC
0x40ade4  mov     ecx, [ebp+arg_0]
0x40ade7  mov     eax, [edi+30h]
0x40adea  mov     [ecx], eax
0x40adec  mov     eax, [edi+38h]
0x40adef  mov     [ecx+4], eax
0x40adf2  mov     eax, [edi+40h]
0x40adf5  mov     [ecx+8], eax
0x40adf8  xor     eax, eax
0x40adfa  jmp     short loc_40AE62
0x40adfc  movzx   ecx, byte_43EE81
0x40ae03  neg     ecx
0x40ae05  sbb     ecx, ecx
0x40ae07  and     ecx, offset dword_43ED80
0x40ae0d  jz      short loc_40AE5D
0x40ae0f  push    esi
0x40ae10  push    7
0x40ae12  pop     edx
0x40ae13  push    5
0x40ae15  pop     eax
0x40ae16  push    eax
0x40ae17  push    edx
0x40ae18  mov     [ebp+var_14], ecx
0x40ae1b  mov     [ebp+var_10], edx
0x40ae1e  mov     [ebp+var_C], eax
0x40ae21  call    sub_4071AF
0x40ae26  mov     [ebp+var_8], eax
0x40ae29  mov     eax, [edi]
0x40ae2b  mov     esi, [eax+4]
0x40ae2e  lea     eax, [ebp+var_4]
0x40ae31  push    eax
0x40ae32  mov     ecx, esi
0x40ae34  call    ds:___guard_check_icall_fptr
0x40ae3a  mov     ecx, edi
0x40ae3c  call    esi
0x40ae3e  push    dword ptr [eax]
0x40ae40  lea     eax, [ebp+var_14]
0x40ae43  push    offset aGetupdatessupp; "[GetUpdatesSuppressedTimes][%s][Missing"...
0x40ae48  push    eax
0x40ae49  call    sub_404564
0x40ae4e  mov     ecx, [ebp+var_4]
0x40ae51  add     esp, 0Ch
0x40ae54  lea     ecx, [ecx-10h]
0x40ae57  call    sub_4015D2
0x40ae5c  pop     esi
0x40ae5d  mov     eax, 80004005h
0x40ae62  pop     edi
0x40ae63  leave
0x40ae64  retn    4
```
