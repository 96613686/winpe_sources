# SdbpGetMergeSdbsDisabled

- ea: `0x140046180`
- end: `0x14004626d`
- name: `SdbpGetMergeSdbsDisabled`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14004506c`

## callees

- `0x140004469`
- `0x14003e364`
- `0x140046180`
- `0x140046440`
- `0x140046660`

## string_xrefs

- `0x1400461ac`: `Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\SdbUpdates`
- `0x1400461d0`: `AslRegistryGetKey failed to open SdbUpdates key [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetMergeSdbsDisabled(_DWORD *a1)
{
  int Key; // eax
  char *v3; // rdi
  unsigned int v4; // ebx
  int UInt32; // eax
  int v7; // [rsp+48h] [rbp+10h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  Handle = 0;
  Key = AslRegistryGetKey(
          &Handle,
          L"Software\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\SdbUpdates",
          0x80000100,
          1);
  v3 = (char *)Handle;
  v4 = Key;
  if ( Key >= 0 )
  {
    UInt32 = AslRegistryGetUInt32(&v7, Handle, L"DisableDoubleQuerySdbs");
    v4 = UInt32;
    if ( UInt32 == -1073741772 )
    {
      v4 = 0;
      *a1 = 0;
    }
    else if ( UInt32 >= 0 )
    {
      v4 = 0;
      *a1 = v7 != 0;
    }
    else
    {
      AslLogCallPrintf(1, "SdbpGetMergeSdbsDisabled", 1128, "Failed to query reg value.");
    }
  }
  else if ( Key != -1073741772 )
  {
    AslLogCallPrintf(1, "SdbpGetMergeSdbsDisabled", 1116, "AslRegistryGetKey failed to open SdbUpdates key [%x]", Key);
  }
  if ( (unsigned __int64)(v3 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    ZwClose_0(v3);
  return v4;
}

```

## disassembly

```asm
0x140046180  mov     rax, rsp
0x140046183  mov     [rax+8], rbx
0x140046187  mov     [rax+20h], rsi
0x14004618b  push    rdi
0x14004618c  sub     rsp, 30h
0x140046190  mov     rsi, rcx
0x140046193  mov     dword ptr [rax+10h], 0
0x14004619a  lea     rcx, [rax+18h]
0x14004619e  mov     qword ptr [rax+18h], 0
0x1400461a6  mov     r9d, 1
0x1400461ac  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1400461b3  mov     r8d, 80000100h
0x1400461b9  call    AslRegistryGetKey
0x1400461be  mov     rdi, [rsp+38h+Handle]
0x1400461c3  mov     ebx, eax
0x1400461c5  test    eax, eax
0x1400461c7  jns     short loc_1400461F4
0x1400461c9  cmp     eax, 0C0000034h
0x1400461ce  jz      short loc_140046248
0x1400461d0  lea     r9, aAslregistryget_4; "AslRegistryGetKey failed to open SdbUpd"...
0x1400461d7  mov     [rsp+38h+var_18], eax
0x1400461db  mov     r8d, 45Ch
0x1400461e1  lea     rdx, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled"
0x1400461e8  mov     ecx, 1
0x1400461ed  call    AslLogCallPrintf
0x1400461f2  jmp     short loc_140046248
0x1400461f4  lea     r8, aDisabledoubleq; "DisableDoubleQuerySdbs"
0x1400461fb  mov     rdx, rdi
0x1400461fe  lea     rcx, [rsp+38h+arg_8]
0x140046203  call    AslRegistryGetUInt32
0x140046208  mov     ebx, eax
0x14004620a  cmp     eax, 0C0000034h
0x14004620f  jnz     short loc_140046217
0x140046211  xor     ebx, ebx
0x140046213  mov     [rsi], ebx
0x140046215  jmp     short loc_140046248
0x140046217  test    eax, eax
0x140046219  jns     short loc_14004623B
0x14004621b  lea     r9, aFailedToQueryR_1; "Failed to query reg value."
0x140046222  mov     r8d, 468h
0x140046228  lea     rdx, aSdbpgetmergesd_0; "SdbpGetMergeSdbsDisabled"
0x14004622f  mov     ecx, 1
0x140046234  call    AslLogCallPrintf
0x140046239  jmp     short loc_140046248
0x14004623b  xor     eax, eax
0x14004623d  cmp     [rsp+38h+arg_8], eax
0x140046241  setnz   al
0x140046244  xor     ebx, ebx
0x140046246  mov     [rsi], eax
0x140046248  lea     rax, [rdi-1]
0x14004624c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140046250  ja      short loc_14004625A
0x140046252  mov     rcx, rdi; Handle
0x140046255  call    ZwClose_0
0x14004625a  mov     rsi, [rsp+38h+arg_18]
0x14004625f  mov     eax, ebx
0x140046261  mov     rbx, [rsp+38h+arg_0]
0x140046266  add     rsp, 30h
0x14004626a  pop     rdi
0x14004626b  retn
```
