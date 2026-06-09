# AiRegReadDwordValue

- ea: `0x1800086b0`
- end: `0x180008794`
- name: `AiRegReadDwordValue`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180004154`

## callees

- `0x180003fd4`
- `0x180008668`
- `0x1800086b0`

## import_xrefs

- `ntdll!NtClose` at `0x180008783`
- `ntdll!NtClose` at `0x180008783`
- `ntdll!RtlFreeHeap` at `0x1800086fb`
- `ntdll!RtlFreeHeap` at `0x180008773`
- `ntdll!RtlFreeHeap` at `0x1800086fb`
- `ntdll!RtlFreeHeap` at `0x180008773`
- `ntdll!NtQueryValueKey` at `0x18000872f`
- `ntdll!NtQueryValueKey` at `0x18000872f`

## pseudocode

```c
__int64 __fastcall AiRegReadDwordValue(__int64 a1, struct _UNICODE_STRING *a2, struct _UNICODE_STRING *a3, _DWORD *a4)
{
  _DWORD *v6; // rdi
  NTSTATUS v7; // ebx
  ULONG Length; // ebx
  NTSTATUS v9; // eax
  HANDLE KeyHandle; // [rsp+30h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+70h] [rbp+8h] BYREF
  int v13; // [rsp+74h] [rbp+Ch]

  v13 = HIDWORD(a1);
  KeyHandle = 0;
  ResultLength = 48;
  v6 = 0;
  v7 = AiRegOpenKey(a1, a2, (__int64)a3, &KeyHandle);
  if ( v7 >= 0 )
  {
    do
    {
      Length = ResultLength;
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
      v6 = (_DWORD *)AiAlloc(Length);
      if ( !v6 )
      {
        v7 = -1073741801;
        goto LABEL_10;
      }
      v9 = NtQueryValueKey(KeyHandle, a3, KeyValuePartialInformation, v6, Length, &ResultLength);
      v7 = v9;
    }
    while ( v9 == -2147483643 );
    if ( v9 >= 0 )
    {
      if ( v6[1] == 4 && v6[2] == 4 )
        *a4 = v6[3];
      else
        v7 = -1073741788;
    }
  }
LABEL_10:
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800086b0  mov     rax, rsp
0x1800086b3  mov     [rax+8], rcx
0x1800086b7  push    rbx
0x1800086b8  push    rbp
0x1800086b9  push    rsi
0x1800086ba  push    rdi
0x1800086bb  sub     rsp, 48h
0x1800086bf  mov     rsi, r9
0x1800086c2  mov     qword ptr [rax-38h], 0
0x1800086ca  lea     r9, [rax-38h]
0x1800086ce  mov     dword ptr [rax+8], 30h ; '0'
0x1800086d5  mov     rbp, r8
0x1800086d8  xor     edi, edi
0x1800086da  call    AiRegOpenKey
0x1800086df  mov     ebx, eax
0x1800086e1  test    eax, eax
0x1800086e3  js      short loc_180008761
0x1800086e5  mov     rcx, gs:60h
0x1800086ee  mov     r8, rdi; P
0x1800086f1  mov     ebx, [rsp+68h+arg_0]
0x1800086f5  xor     edx, edx; Flags
0x1800086f7  mov     rcx, [rcx+30h]; HeapHandle
0x1800086fb  call    cs:__imp_RtlFreeHeap
0x180008701  mov     ecx, ebx
0x180008703  call    AiAlloc
0x180008708  mov     rdi, rax
0x18000870b  test    rax, rax
0x18000870e  jz      short loc_18000875C
0x180008710  mov     rcx, [rsp+68h+KeyHandle]; KeyHandle
0x180008715  lea     rax, [rsp+68h+arg_0]
0x18000871a  mov     [rsp+68h+ResultLength], rax; ResultLength
0x18000871f  mov     r9, rdi; KeyValueInformation
0x180008722  mov     r8d, 2; KeyValueInformationClass
0x180008728  mov     [rsp+68h+Length], ebx; Length
0x18000872c  mov     rdx, rbp; ValueName
0x18000872f  call    cs:__imp_NtQueryValueKey
0x180008735  mov     ebx, eax
0x180008737  cmp     eax, 80000005h
0x18000873c  jz      short loc_1800086E5
0x18000873e  test    eax, eax
0x180008740  js      short loc_180008761
0x180008742  cmp     dword ptr [rdi+4], 4
0x180008746  jnz     short loc_180008755
0x180008748  cmp     dword ptr [rdi+8], 4
0x18000874c  jnz     short loc_180008755
0x18000874e  mov     eax, [rdi+0Ch]
0x180008751  mov     [rsi], eax
0x180008753  jmp     short loc_180008761
0x180008755  mov     ebx, 0C0000024h
0x18000875a  jmp     short loc_180008761
0x18000875c  mov     ebx, 0C0000017h
0x180008761  mov     rcx, gs:60h
0x18000876a  mov     r8, rdi; P
0x18000876d  xor     edx, edx; Flags
0x18000876f  mov     rcx, [rcx+30h]; HeapHandle
0x180008773  call    cs:__imp_RtlFreeHeap
0x180008779  mov     rcx, [rsp+68h+KeyHandle]; Handle
0x18000877e  test    rcx, rcx
0x180008781  jz      short loc_180008789
0x180008783  call    cs:__imp_NtClose
0x180008789  mov     eax, ebx
0x18000878b  add     rsp, 48h
0x18000878f  pop     rdi
0x180008790  pop     rsi
0x180008791  pop     rbp
0x180008792  pop     rbx
0x180008793  retn
```
