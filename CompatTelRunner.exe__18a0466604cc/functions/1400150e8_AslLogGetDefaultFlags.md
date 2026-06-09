# AslLogGetDefaultFlags

- ea: `0x1400150e8`
- end: `0x1400151aa`
- name: `AslLogGetDefaultFlags`
- size: `194`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400145a4`

## callees

- `0x1400128e8`
- `0x140012dd0`
- `0x1400150e8`

## import_xrefs

- `ntdll!ZwClose` at `0x140015148`
- `ntdll!ZwClose` at `0x140015192`
- `ntdll!ZwClose` at `0x140015148`
- `ntdll!ZwClose` at `0x140015192`

## string_xrefs

- `0x140015115`: `\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x140015156`: `\OSDATA\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`

## pseudocode

```c
__int64 AslLogGetDefaultFlags()
{
  unsigned int v0; // edi
  HANDLE v1; // rbx
  int Key; // eax
  int UInt32; // eax
  int v4; // eax
  unsigned int v6; // [rsp+40h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+18h] BYREF

  v0 = 0;
  v1 = 0;
  v6 = 0;
  Handle = 0;
  if ( byte_1400C90E0 )
  {
    v0 = dword_1400C90D8;
  }
  else
  {
    Key = AslRegistryGetKey(&Handle, L"\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
    v1 = Handle;
    if ( Key < 0 || (UInt32 = AslRegistryGetUInt32(&v6, Handle), v0 = v6, UInt32 < 0) )
    {
      if ( v1 )
      {
        ZwClose(v1);
        Handle = 0;
      }
      v4 = AslRegistryGetKey(&Handle, L"\\OSDATA\\Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags");
      v1 = Handle;
      if ( v4 >= 0 )
      {
        AslRegistryGetUInt32(&v6, Handle);
        v0 = v6;
      }
    }
  }
  dword_1400C90D8 = v0;
  byte_1400C90E0 = 1;
  if ( v1 )
    ZwClose(v1);
  return v0;
}

```

## disassembly

```asm
0x1400150e8  mov     [rsp-8+arg_10], rbx
0x1400150ed  mov     [rsp-8+arg_18], rdi
0x1400150f2  push    rbp
0x1400150f3  mov     rbp, rsp
0x1400150f6  sub     rsp, 30h
0x1400150fa  xor     edi, edi
0x1400150fc  xor     ebx, ebx
0x1400150fe  cmp     cs:byte_1400C90E0, bl
0x140015104  mov     [rbp+arg_0], edi
0x140015107  mov     [rbp+Handle], rbx
0x14001510b  jz      short loc_140015115
0x14001510d  mov     edi, cs:dword_1400C90D8
0x140015113  jmp     short loc_14001517D
0x140015115  lea     rdx, aSoftwareMicros_0; "\\Software\\Microsoft\\Windows NT\\Curr"...
0x14001511c  lea     rcx, [rbp+Handle]
0x140015120  call    AslRegistryGetKey
0x140015125  mov     rbx, [rbp+Handle]
0x140015129  test    eax, eax
0x14001512b  js      short loc_140015140
0x14001512d  mov     rdx, rbx
0x140015130  lea     rcx, [rbp+arg_0]
0x140015134  call    AslRegistryGetUInt32
0x140015139  mov     edi, [rbp+arg_0]
0x14001513c  test    eax, eax
0x14001513e  jns     short loc_14001517D
0x140015140  test    rbx, rbx
0x140015143  jz      short loc_140015156
0x140015145  mov     rcx, rbx; Handle
0x140015148  call    cs:__imp_ZwClose
0x14001514e  mov     [rbp+Handle], 0
0x140015156  lea     rdx, aOsdataSoftware; "\\OSDATA\\Software\\Microsoft\\Windows "...
0x14001515d  lea     rcx, [rbp+Handle]
0x140015161  call    AslRegistryGetKey
0x140015166  mov     rbx, [rbp+Handle]
0x14001516a  test    eax, eax
0x14001516c  js      short loc_14001517D
0x14001516e  mov     rdx, rbx
0x140015171  lea     rcx, [rbp+arg_0]
0x140015175  call    AslRegistryGetUInt32
0x14001517a  mov     edi, [rbp+arg_0]
0x14001517d  mov     cs:dword_1400C90D8, edi
0x140015183  mov     cs:byte_1400C90E0, 1
0x14001518a  test    rbx, rbx
0x14001518d  jz      short loc_140015198
0x14001518f  mov     rcx, rbx; Handle
0x140015192  call    cs:__imp_ZwClose
0x140015198  mov     rbx, [rsp+30h+arg_10]
0x14001519d  mov     eax, edi
0x14001519f  mov     rdi, [rsp+30h+arg_18]
0x1400151a4  add     rsp, 30h
0x1400151a8  pop     rbp
0x1400151a9  retn
```
