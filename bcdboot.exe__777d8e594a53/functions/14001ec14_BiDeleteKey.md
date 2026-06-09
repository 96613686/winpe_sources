# BiDeleteKey

- ea: `0x14001ec14`
- end: `0x14001ecd9`
- name: `BiDeleteKey`
- size: `197`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140013b9c`
- `0x140018b54`
- `0x140019990`
- `0x14001a964`
- `0x14001ec14`

## callees

- `0x14001e5e4`
- `0x14001ec14`
- `0x14001ee20`
- `0x14001f980`

## import_xrefs

- `ntdll!ZwClose` at `0x14001ecc8`
- `ntdll!ZwClose` at `0x14001ecc8`
- `ntdll!ZwDeleteKey` at `0x14001ecb9`
- `ntdll!ZwDeleteKey` at `0x14001ecb9`
- `ntdll!RtlFreeHeap` at `0x14001ecb0`
- `ntdll!RtlFreeHeap` at `0x14001ecb0`

## pseudocode

```c
__int64 __fastcall BiDeleteKey(__int64 a1)
{
  void *v1; // rbx
  int v2; // eax
  _QWORD *v3; // r14
  __int64 i; // rdi
  NTSTATUS v5; // edi
  unsigned int v7; // [rsp+40h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp+10h] BYREF
  PVOID P; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  v1 = (void *)(a1 & 0xFFFFFFFFFFFFFFFDuLL);
  Handle = 0;
  P = 0;
  v2 = BiEnumerateSubKeys(a1 & 0xFFFFFFFFFFFFFFFDuLL, &P, &v7);
  v3 = P;
  if ( v2 >= 0 )
  {
    for ( i = 0; (unsigned int)i < v7; i = (unsigned int)(i + 1) )
    {
      if ( (int)BiOpenKey(v1, v3[i], 983103, &Handle) >= 0 && (int)BiDeleteKey(Handle) < 0 )
        BiCloseKey(Handle);
    }
  }
  if ( v3 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
  v5 = ZwDeleteKey(v1);
  if ( v5 >= 0 )
    ZwClose(v1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001ec14  mov     rax, rsp
0x14001ec17  push    rbx
0x14001ec18  push    rdi
0x14001ec19  push    r14
0x14001ec1b  sub     rsp, 20h
0x14001ec1f  mov     rbx, rcx
0x14001ec22  mov     dword ptr [rax+8], 0
0x14001ec29  and     rbx, 0FFFFFFFFFFFFFFFDh
0x14001ec2d  mov     qword ptr [rax+10h], 0
0x14001ec35  mov     rcx, rbx
0x14001ec38  mov     qword ptr [rax+18h], 0
0x14001ec40  lea     r8, [rax+8]
0x14001ec44  lea     rdx, [rax+18h]
0x14001ec48  call    BiEnumerateSubKeys
0x14001ec4d  mov     r14, [rsp+38h+P]
0x14001ec52  test    eax, eax
0x14001ec54  js      short loc_14001EC99
0x14001ec56  xor     edi, edi
0x14001ec58  cmp     [rsp+38h+arg_0], edi
0x14001ec5c  jbe     short loc_14001EC99
0x14001ec5e  mov     rdx, [r14+rdi*8]
0x14001ec62  lea     r9, [rsp+38h+Handle]
0x14001ec67  mov     r8d, 0F003Fh
0x14001ec6d  mov     rcx, rbx
0x14001ec70  call    BiOpenKey
0x14001ec75  test    eax, eax
0x14001ec77  js      short loc_14001EC91
0x14001ec79  mov     rcx, [rsp+38h+Handle]
0x14001ec7e  call    BiDeleteKey
0x14001ec83  test    eax, eax
0x14001ec85  jns     short loc_14001EC91
0x14001ec87  mov     rcx, [rsp+38h+Handle]; Handle
0x14001ec8c  call    BiCloseKey
0x14001ec91  inc     edi
0x14001ec93  cmp     edi, [rsp+38h+arg_0]
0x14001ec97  jb      short loc_14001EC5E
0x14001ec99  test    r14, r14
0x14001ec9c  jz      short loc_14001ECB6
0x14001ec9e  mov     rcx, gs:60h
0x14001eca7  mov     r8, r14; P
0x14001ecaa  xor     edx, edx; Flags
0x14001ecac  mov     rcx, [rcx+30h]; HeapHandle
0x14001ecb0  call    cs:__imp_RtlFreeHeap
0x14001ecb6  mov     rcx, rbx; KeyHandle
0x14001ecb9  call    cs:__imp_ZwDeleteKey
0x14001ecbf  mov     edi, eax
0x14001ecc1  test    eax, eax
0x14001ecc3  js      short loc_14001ECCE
0x14001ecc5  mov     rcx, rbx; Handle
0x14001ecc8  call    cs:__imp_ZwClose
0x14001ecce  mov     eax, edi
0x14001ecd0  add     rsp, 20h
0x14001ecd4  pop     r14
0x14001ecd6  pop     rdi
0x14001ecd7  pop     rbx
0x14001ecd8  retn
```
