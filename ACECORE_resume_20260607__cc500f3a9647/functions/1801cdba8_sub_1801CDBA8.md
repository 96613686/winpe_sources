# sub_1801CDBA8

- ea: `0x1801cdba8`
- end: `0x1801cdc45`
- name: `sub_1801CDBA8`
- size: `157`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180024054`
- `0x180058628`
- `0x180058834`
- `0x1801af4d0`
- `0x1801cb900`
- `0x1801cdc48`
- `0x1801cdcc0`

## callees

- `0x1801cdab4`
- `0x1801cdba8`
- `0x1801ce930`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1801cdbb7`
- `KERNEL32!GetModuleHandleW` at `0x1801cdbb7`
- `MSO!MsoLoadLocalizedLibraryEx` at `0x1801cdc36`
- `Mso30Win32Client!Mso30Win32Client_60614` at `0x1801cdc24`
- `Mso30Win32Client!Mso30Win32Client_60614` at `0x1801cdc24`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1801cdbf1`
- `Mso20Win32Client!Mso20Win32Client_52497` at `0x1801cdbf1`

## string_xrefs

- `0x1801cdbb0`: `mso.dll`

## pseudocode

```c
__int64 __fastcall sub_1801CDBA8(unsigned int a1)
{
  _QWORD *v2; // rax

  if ( (GetModuleHandleW(L"mso.dll") || !sub_1801CDAB4()) && !sub_1801CE930((__int64)&qword_18022A228, 0) )
    return 0;
  v2 = (_QWORD *)qword_18025EDC0;
  if ( !qword_18025EDC0 )
  {
    v2 = (_QWORD *)Mso20Win32Client_52497(8, 2);
    if ( v2 )
      *v2 = &OfficeGimmeUser::`vftable';
    qword_18025EDC0 = (__int64)v2;
    if ( !v2 )
      return 0;
  }
  Mso30Win32Client_60614(0x80000, &qword_180226F90, v2, 0x80000);
  return MsoLoadLocalizedLibraryEx(a1, 0, 0);
}

```

## disassembly

```asm
0x1801cdba8  push    rbx
0x1801cdbaa  sub     rsp, 20h
0x1801cdbae  mov     ebx, ecx
0x1801cdbb0  lea     rcx, aMsoDll_0; "mso.dll"
0x1801cdbb7  call    cs:GetModuleHandleW
0x1801cdbbd  test    rax, rax
0x1801cdbc0  jnz     short loc_1801CDBCC
0x1801cdbc2  call    sub_1801CDAB4
0x1801cdbc7  test    rax, rax
0x1801cdbca  jnz     short loc_1801CDBDF
0x1801cdbcc  xor     edx, edx
0x1801cdbce  lea     rcx, qword_18022A228
0x1801cdbd5  call    sub_1801CE930
0x1801cdbda  test    rax, rax
0x1801cdbdd  jz      short loc_1801CDC3D
0x1801cdbdf  mov     rax, cs:qword_18025EDC0
0x1801cdbe6  test    rax, rax
0x1801cdbe9  jnz     short loc_1801CDC12
0x1801cdbeb  lea     edx, [rax+2]
0x1801cdbee  lea     ecx, [rax+8]
0x1801cdbf1  call    cs:Mso20Win32Client_52497
0x1801cdbf7  test    rax, rax
0x1801cdbfa  jz      short loc_1801CDC06
0x1801cdbfc  lea     rcx, ??_7OfficeGimmeUser@@6B@; const OfficeGimmeUser::`vftable'
0x1801cdc03  mov     [rax], rcx
0x1801cdc06  mov     cs:qword_18025EDC0, rax
0x1801cdc0d  test    rax, rax
0x1801cdc10  jz      short loc_1801CDC3D
0x1801cdc12  mov     ecx, 80000h
0x1801cdc17  lea     rdx, qword_180226F90
0x1801cdc1e  mov     r9d, ecx
0x1801cdc21  mov     r8, rax
0x1801cdc24  call    cs:Mso30Win32Client_60614
0x1801cdc2a  xor     r8d, r8d
0x1801cdc2d  xor     edx, edx
0x1801cdc2f  mov     ecx, ebx
0x1801cdc31  add     rsp, 20h
0x1801cdc35  pop     rbx
0x1801cdc36  jmp     cs:MsoLoadLocalizedLibraryEx
0x1801cdc3d  xor     eax, eax
0x1801cdc3f  add     rsp, 20h
0x1801cdc43  pop     rbx
0x1801cdc44  retn
```
