# AslpPathWildcardAllocMatchNode

- ea: `0x18006f9ec`
- end: `0x18006fc72`
- name: `AslpPathWildcardAllocMatchNode`
- size: `646`
- prototype: `__int64 __fastcall(unsigned __int16 *, _WORD *, _WORD *, int, __int64, unsigned __int16)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004afb0`
- `0x18006c020`

## callees

- `0x1800197d4`
- `0x1800303b0`
- `0x18006f9ec`
- `0x18006fd6c`
- `0x180070294`
- `0x180070334`
- `0x1800703f0`
- `0x1800704a4`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18006fae7`
- `ntdll!RtlAllocateHeap` at `0x18006fae7`
- `ntdll!ZwOpenFile` at `0x18006fc22`
- `ntdll!ZwOpenFile` at `0x18006fc22`

## string_xrefs

- `0x18006fc3f`: `AslpPathWildcardAllocMatchNode`
- `0x18006fb11`: `RtlUnicodeStringCopy failed [%x]`
- `0x18006fc2e`: `Failed to open dir [%x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AslpPathWildcardAllocMatchNode(
        unsigned __int16 *a1,
        _WORD *a2,
        _WORD *a3,
        int a4,
        __int64 a5,
        unsigned __int16 a6)
{
  NTSTATUS v8; // edi
  const char *v9; // r9
  int v10; // r8d
  unsigned int v11; // ecx
  PVOID Heap; // rax
  __int16 v13; // bx
  __int64 v15; // [rsp+30h] [rbp-50h] BYREF
  __int64 v16; // [rsp+38h] [rbp-48h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+A0h] [rbp+20h] BYREF
  __int64 v20; // [rsp+B0h] [rbp+30h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_QWORD *)a1 = 0;
  *((_QWORD *)a1 + 1) = 0;
  *((_QWORD *)a1 + 3) = 0;
  while ( 1 )
  {
    *((_QWORD *)a1 + 2) = a3;
    if ( !*a3 )
      break;
    ++a3;
  }
  *((_QWORD *)a1 + 2) = a3 + 1;
  if ( !a3[1] )
  {
    v8 = a4 != 0 ? -1073741638 : -1073741197;
LABEL_27:
    AslpPathWildcardFreeMatchNode(a1);
    return (unsigned int)v8;
  }
  if ( !a4 )
  {
    v8 = -1073741565;
    goto LABEL_27;
  }
  LOWORD(v19) = *a2;
  v8 = RtlUShortAdd((unsigned __int16)v19, a6, &v19);
  if ( v8 < 0 )
  {
    v9 = "RtlUShortAdd failed [%x]";
    v10 = 2886;
LABEL_26:
    AslLogCallPrintf(1, (unsigned int)"AslpPathWildcardAllocMatchNode", v10, (_DWORD)v9);
    goto LABEL_27;
  }
  v8 = RtlUShortAdd((unsigned __int16)v19, 4, &v19);
  if ( v8 < 0 )
  {
    v9 = "RtlUShortAdd failed [%x]";
    v10 = 2892;
    goto LABEL_26;
  }
  v11 = (unsigned __int16)v19;
  a1[1] = v19;
  *a1 = 0;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v11);
  *((_QWORD *)a1 + 1) = Heap;
  if ( !Heap )
  {
    v8 = -1073741801;
    goto LABEL_27;
  }
  v8 = RtlUnicodeStringCopy(a1, a2);
  if ( v8 < 0 )
  {
    v9 = "RtlUnicodeStringCopy failed [%x]";
    v10 = 2907;
    goto LABEL_26;
  }
  if ( *(_WORD *)(*((_QWORD *)a1 + 1) + 2 * ((unsigned __int64)*a1 >> 1) - 2) != 92 )
  {
    v15 = 0;
    v19 = 0;
    v20 = 0;
    v8 = RtlUnicodeStringValidateDestWorker(a1, &v15, &v19, &v20);
    if ( v8 < 0
      || (v13 = v20,
          v16 = 0,
          v8 = RtlWideCharArrayCopyStringWorker(
                 (int)v15 + 2 * (int)v20,
                 (int)v19 - (int)v20,
                 (unsigned int)&v16,
                 (unsigned int)L"\\",
                 0x7FFF),
          *a1 = 2 * (v16 + v13),
          v8 < 0) )
    {
      v9 = "RtlUnicodeStringCatString failed [%x]";
      v10 = 2923;
      goto LABEL_26;
    }
  }
  if ( a5 )
  {
    if ( a6 )
    {
      v8 = RtlUnicodeStringCbCatStringN(a1, a5, a6);
      if ( v8 < 0 )
      {
        v9 = "RtlUnicodeStringCbCatStringN failed [%x]";
        v10 = 2931;
        goto LABEL_26;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenFile((PHANDLE)a1 + 3, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x21u);
  if ( v8 < 0 )
  {
    v9 = "Failed to open dir [%x]";
    v10 = 2945;
    goto LABEL_26;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006f9ec  mov     [rsp-18h+arg_8], rbx
0x18006f9f1  mov     [rsp-18h+arg_18], rsi
0x18006f9f6  push    rbp
0x18006f9f7  push    rdi
0x18006f9f8  push    r15
0x18006f9fa  mov     rbp, rsp
0x18006f9fd  sub     rsp, 80h
0x18006fa04  xorps   xmm0, xmm0
0x18006fa07  xor     eax, eax
0x18006fa09  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006fa0d  xor     r15d, r15d
0x18006fa10  mov     rbx, rdx
0x18006fa13  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18006fa17  mov     rsi, rcx
0x18006fa1a  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006fa1e  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18006fa22  mov     [rcx], r15
0x18006fa25  mov     [rcx+8], r15
0x18006fa29  mov     [rcx+18h], r15
0x18006fa2d  jmp     short loc_18006FA33
0x18006fa2f  add     r8, 2
0x18006fa33  mov     [rcx+10h], r8
0x18006fa37  cmp     [r8], r15w
0x18006fa3b  jnz     short loc_18006FA2F
0x18006fa3d  lea     rax, [r8+2]
0x18006fa41  mov     [rcx+10h], rax
0x18006fa45  cmp     [rax], r15w
0x18006fa49  jnz     short loc_18006FA61
0x18006fa4b  neg     r9d
0x18006fa4e  sbb     edi, edi
0x18006fa50  and     edi, 0FFFFFE47h
0x18006fa56  add     edi, 0C0000273h
0x18006fa5c  jmp     loc_18006FC50
0x18006fa61  test    r9d, r9d
0x18006fa64  jnz     short loc_18006FA70
0x18006fa66  mov     edi, 0C0000103h
0x18006fa6b  jmp     loc_18006FC50
0x18006fa70  movzx   ecx, word ptr [rdx]
0x18006fa73  lea     r8, [rbp+arg_0]
0x18006fa77  movzx   edx, [rbp+arg_28]
0x18006fa7b  mov     word ptr [rbp+arg_0], cx
0x18006fa7f  call    RtlUShortAdd
0x18006fa84  mov     edi, eax
0x18006fa86  test    eax, eax
0x18006fa88  jns     short loc_18006FA9C
0x18006fa8a  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x18006fa91  mov     r8d, 0B46h
0x18006fa97  jmp     loc_18006FC3B
0x18006fa9c  movzx   ecx, word ptr [rbp+arg_0]
0x18006faa0  lea     r8, [rbp+arg_0]
0x18006faa4  mov     edx, 4
0x18006faa9  call    RtlUShortAdd
0x18006faae  mov     edi, eax
0x18006fab0  test    eax, eax
0x18006fab2  jns     short loc_18006FAC6
0x18006fab4  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x18006fabb  mov     r8d, 0B4Ch
0x18006fac1  jmp     loc_18006FC3B
0x18006fac6  movzx   ecx, word ptr [rbp+arg_0]
0x18006faca  mov     edx, 8; Flags
0x18006facf  mov     [rsi+2], cx
0x18006fad3  mov     r8d, ecx; Size
0x18006fad6  mov     [rsi], r15w
0x18006fada  mov     rcx, gs:60h
0x18006fae3  mov     rcx, [rcx+30h]; HeapHandle
0x18006fae7  call    cs:__imp_RtlAllocateHeap
0x18006faed  mov     [rsi+8], rax
0x18006faf1  test    rax, rax
0x18006faf4  jnz     short loc_18006FB00
0x18006faf6  mov     edi, 0C0000017h
0x18006fafb  jmp     loc_18006FC50
0x18006fb00  mov     rdx, rbx
0x18006fb03  mov     rcx, rsi
0x18006fb06  call    RtlUnicodeStringCopy
0x18006fb0b  mov     edi, eax
0x18006fb0d  test    eax, eax
0x18006fb0f  jns     short loc_18006FB23
0x18006fb11  lea     r9, aRtlunicodestri_1; "RtlUnicodeStringCopy failed [%x]"
0x18006fb18  mov     r8d, 0B5Bh
0x18006fb1e  jmp     loc_18006FC3B
0x18006fb23  movzx   ecx, word ptr [rsi]
0x18006fb26  mov     rax, [rsi+8]
0x18006fb2a  shr     rcx, 1
0x18006fb2d  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18006fb33  jz      short loc_18006FBB1
0x18006fb35  lea     r9, [rbp+arg_10]
0x18006fb39  mov     [rbp+var_50], r15
0x18006fb3d  lea     r8, [rbp+arg_0]
0x18006fb41  mov     [rbp+arg_0], r15
0x18006fb45  lea     rdx, [rbp+var_50]
0x18006fb49  mov     [rbp+arg_10], r15
0x18006fb4d  mov     rcx, rsi
0x18006fb50  call    RtlUnicodeStringValidateDestWorker
0x18006fb55  mov     edi, eax
0x18006fb57  test    eax, eax
0x18006fb59  js      short loc_18006FB9B
0x18006fb5b  mov     rbx, [rbp+arg_10]
0x18006fb5f  lea     r9, SubBlock; "\\"
0x18006fb66  mov     rax, [rbp+var_50]
0x18006fb6a  lea     r8, [rbp+var_48]
0x18006fb6e  mov     rdx, [rbp+arg_0]
0x18006fb72  sub     rdx, rbx
0x18006fb75  mov     [rbp+var_48], r15
0x18006fb79  mov     qword ptr [rsp+80h+ShareAccess], 7FFFh
0x18006fb82  lea     rcx, [rax+rbx*2]
0x18006fb86  call    RtlWideCharArrayCopyStringWorker
0x18006fb8b  add     bx, word ptr [rbp+var_48]
0x18006fb8f  mov     edi, eax
0x18006fb91  add     bx, bx
0x18006fb94  mov     [rsi], bx
0x18006fb97  test    eax, eax
0x18006fb99  jns     short loc_18006FBB1
0x18006fb9b  mov     [rsp+80h+ShareAccess], edi
0x18006fb9f  lea     r9, aRtlunicodestri_0; "RtlUnicodeStringCatString failed [%x]"
0x18006fba6  mov     r8d, 0B6Bh
0x18006fbac  jmp     loc_18006FC3F
0x18006fbb1  mov     rdx, [rbp+arg_20]
0x18006fbb5  test    rdx, rdx
0x18006fbb8  jz      short loc_18006FBE3
0x18006fbba  cmp     [rbp+arg_28], r15w
0x18006fbbf  jbe     short loc_18006FBE3
0x18006fbc1  movzx   r8d, [rbp+arg_28]
0x18006fbc6  mov     rcx, rsi
0x18006fbc9  call    RtlUnicodeStringCbCatStringN
0x18006fbce  mov     edi, eax
0x18006fbd0  test    eax, eax
0x18006fbd2  jns     short loc_18006FBE3
0x18006fbd4  lea     r9, aRtlunicodestri; "RtlUnicodeStringCbCatStringN failed [%x"...
0x18006fbdb  mov     r8d, 0B73h
0x18006fbe1  jmp     short loc_18006FC3B
0x18006fbe3  xorps   xmm0, xmm0
0x18006fbe6  mov     [rsp+80h+OpenOptions], 21h ; '!'; OpenOptions
0x18006fbee  lea     rcx, [rsi+18h]; FileHandle
0x18006fbf2  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006fbf9  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18006fbfd  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x18006fc01  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006fc05  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006fc0c  mov     edx, 100001h; DesiredAccess
0x18006fc11  mov     [rbp+ObjectAttributes.ObjectName], rsi
0x18006fc15  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006fc1a  mov     [rsp+80h+ShareAccess], 1; ShareAccess
0x18006fc22  call    cs:__imp_ZwOpenFile
0x18006fc28  mov     edi, eax
0x18006fc2a  test    eax, eax
0x18006fc2c  jns     short loc_18006FC58
0x18006fc2e  lea     r9, aFailedToOpenDi; "Failed to open dir [%x]"
0x18006fc35  mov     r8d, 0B81h
0x18006fc3b  mov     [rsp+80h+ShareAccess], eax
0x18006fc3f  lea     rdx, aAslppathwildca_7; "AslpPathWildcardAllocMatchNode"
0x18006fc46  mov     ecx, 1
0x18006fc4b  call    AslLogCallPrintf
0x18006fc50  mov     rcx, rsi
0x18006fc53  call    AslpPathWildcardFreeMatchNode
0x18006fc58  lea     r11, [rsp+80h+var_s0]
0x18006fc60  mov     eax, edi
0x18006fc62  mov     rbx, [r11+28h]
0x18006fc66  mov     rsi, [r11+38h]
0x18006fc6a  mov     rsp, r11
0x18006fc6d  pop     r15
0x18006fc6f  pop     rdi
0x18006fc70  pop     rbp
0x18006fc71  retn
```
