# BiDoesHiveKeyExist

- ea: `0x14001ed70`
- end: `0x14001ee18`
- name: `BiDoesHiveKeyExist`
- size: `168`
- prototype: `bool __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14001af00`

## callees

- `0x14001ed70`
- `0x14001fb48`

## import_xrefs

- `msvcrt!wcschr` at `0x14001ed93`
- `msvcrt!wcschr` at `0x14001ed93`
- `ntdll!ZwClose` at `0x14001edf1`
- `ntdll!ZwClose` at `0x14001edff`
- `ntdll!ZwClose` at `0x14001edf1`
- `ntdll!ZwClose` at `0x14001edff`

## string_xrefs

- `0x14001eda9`: `\Registry\Machine`

## pseudocode

```c
bool __fastcall BiDoesHiveKeyExist(const wchar_t *a1)
{
  void *v1; // rbx
  bool v3; // di
  int v4; // eax
  HANDLE Handle; // [rsp+38h] [rbp+10h] BYREF
  void *v7; // [rsp+40h] [rbp+18h] BYREF

  v1 = 0;
  v7 = 0;
  v3 = 0;
  Handle = 0;
  if ( !wcschr(a1, 0x5Cu) )
  {
    if ( (int)BiOpenKeyNonBcd(0, L"\\Registry\\Machine", 131097, &Handle) >= 0 )
    {
      v4 = BiOpenKeyNonBcd(Handle, a1, 131097, &v7);
      v1 = v7;
      v3 = v4 >= 0;
    }
    if ( Handle )
      ZwClose(Handle);
    if ( v1 )
      ZwClose(v1);
  }
  return v3;
}

```

## disassembly

```asm
0x14001ed70  mov     rax, rsp
0x14001ed73  mov     [rax+8], rbx
0x14001ed77  mov     [rax+20h], rbp
0x14001ed7b  push    rdi
0x14001ed7c  sub     rsp, 20h
0x14001ed80  xor     ebx, ebx
0x14001ed82  mov     rbp, rcx
0x14001ed85  mov     [rax+18h], rbx
0x14001ed89  xor     dil, dil
0x14001ed8c  mov     [rax+10h], rbx
0x14001ed90  lea     edx, [rbx+5Ch]; Ch
0x14001ed93  call    cs:__imp_wcschr
0x14001ed99  test    rax, rax
0x14001ed9c  jnz     short loc_14001EE05
0x14001ed9e  lea     r9, [rsp+28h+Handle]
0x14001eda3  mov     r8d, 20019h
0x14001eda9  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine"
0x14001edb0  xor     ecx, ecx
0x14001edb2  call    BiOpenKeyNonBcd
0x14001edb7  test    eax, eax
0x14001edb9  js      short loc_14001EDE4
0x14001edbb  mov     rcx, [rsp+28h+Handle]
0x14001edc0  lea     r9, [rsp+28h+arg_10]
0x14001edc5  mov     r8d, 20019h
0x14001edcb  mov     rdx, rbp
0x14001edce  call    BiOpenKeyNonBcd
0x14001edd3  lea     ecx, [rbx+1]
0x14001edd6  movzx   edi, dil
0x14001edda  mov     rbx, [rsp+28h+arg_10]
0x14001eddf  test    eax, eax
0x14001ede1  cmovns  edi, ecx
0x14001ede4  cmp     [rsp+28h+Handle], 0
0x14001edea  jz      short loc_14001EDF7
0x14001edec  mov     rcx, [rsp+28h+Handle]; Handle
0x14001edf1  call    cs:__imp_ZwClose
0x14001edf7  test    rbx, rbx
0x14001edfa  jz      short loc_14001EE05
0x14001edfc  mov     rcx, rbx; Handle
0x14001edff  call    cs:__imp_ZwClose
0x14001ee05  mov     rbx, [rsp+28h+arg_0]
0x14001ee0a  mov     al, dil
0x14001ee0d  mov     rbp, [rsp+28h+arg_18]
0x14001ee12  add     rsp, 20h
0x14001ee16  pop     rdi
0x14001ee17  retn
```
