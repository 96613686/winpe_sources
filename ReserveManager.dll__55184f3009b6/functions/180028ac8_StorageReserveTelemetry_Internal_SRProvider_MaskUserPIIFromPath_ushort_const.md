# StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(ushort const *)

- ea: `0x180028ac8`
- end: `0x180028b95`
- name: `?MaskUserPIIFromPath@SRProvider@Internal@StorageReserveTelemetry@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `205`
- prototype: `unsigned __int16 **__fastcall(unsigned __int16 **, _WORD *)`
- caller_count: `6`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180028998`
- `0x18002a440`
- `0x18002ac04`
- `0x18002afa8`
- `0x18002b4e4`
- `0x18002b8c4`

## callees

- `0x180028510`
- `0x180028ac8`
- `0x18002e01c`
- `0x18002f008`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180028b83`
- `ntdll!RtlFreeHeap` at `0x180028b83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028ae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180028ae2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028af4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180028af4`

## pseudocode

```c
unsigned __int16 **__fastcall StorageReserveTelemetry::Internal::SRProvider::MaskUserPIIFromPath(
        unsigned __int16 **a1,
        _WORD *a2)
{
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  char *v7; // rbx
  PVOID P; // [rsp+20h] [rbp-38h] BYREF
  int v10; // [rsp+28h] [rbp-30h]

  P = 0;
  v10 = 0;
  ProcessHeap = GetProcessHeap();
  v5 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x20Au);
  *a1 = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[260] = 0;
    if ( (int)PiiFilter::Initialize((PiiFilter *)&P) >= 0
      && *a2
      && (v6 = *a1) != 0
      && (v10 || (PiiFilter::Initialize((PiiFilter *)&P), v10)) )
    {
      v7 = (char *)P;
      PiiFilterExecute(v6);
    }
    else
    {
      v7 = (char *)P;
    }
    if ( v7 )
    {
      RtlNameValueArray::Free((RtlNameValueArray *)v7);
      RtlNameValueArray::Free((RtlNameValueArray *)(v7 + 48));
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180028ac8  push    rbx
0x180028aca  push    rbp
0x180028acb  push    rsi
0x180028acc  push    rdi
0x180028acd  sub     rsp, 38h
0x180028ad1  xor     ebp, ebp
0x180028ad3  mov     rbx, rdx
0x180028ad6  mov     [rsp+58h+P], rbp
0x180028adb  mov     rsi, rcx
0x180028ade  mov     [rsp+58h+var_30], ebp
0x180028ae2  call    cs:__imp_GetProcessHeap
0x180028ae8  lea     edx, [rbp+8]; dwFlags
0x180028aeb  mov     r8d, 20Ah; dwBytes
0x180028af1  mov     rcx, rax; hHeap
0x180028af4  call    cs:__imp_HeapAlloc
0x180028afa  mov     [rsi], rax
0x180028afd  test    rax, rax
0x180028b00  jz      loc_180028B89
0x180028b06  mov     [rax], bp
0x180028b09  lea     rcx, [rsp+58h+P]; this
0x180028b0e  mov     [rax+208h], bp
0x180028b15  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x180028b1a  test    eax, eax
0x180028b1c  js      short loc_180028B56
0x180028b1e  cmp     [rbx], bp
0x180028b21  jz      short loc_180028B56
0x180028b23  mov     rdi, [rsi]
0x180028b26  test    rdi, rdi
0x180028b29  jz      short loc_180028B56
0x180028b2b  cmp     [rsp+58h+var_30], ebp
0x180028b2f  jnz     short loc_180028B41
0x180028b31  lea     rcx, [rsp+58h+P]; this
0x180028b36  call    ?Initialize@PiiFilter@@QEAAJXZ; PiiFilter::Initialize(void)
0x180028b3b  cmp     [rsp+58h+var_30], ebp
0x180028b3f  jz      short loc_180028B56
0x180028b41  mov     r9, rbx
0x180028b44  mov     rcx, rdi; unsigned __int16 *
0x180028b47  mov     rbx, [rsp+58h+P]
0x180028b4c  mov     r8, rbx
0x180028b4f  call    PiiFilterExecute
0x180028b54  jmp     short loc_180028B5B
0x180028b56  mov     rbx, [rsp+58h+P]
0x180028b5b  test    rbx, rbx
0x180028b5e  jz      short loc_180028B89
0x180028b60  mov     rcx, rbx; this
0x180028b63  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x180028b68  lea     rcx, [rbx+30h]; this
0x180028b6c  call    ?Free@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Free(void)
0x180028b71  mov     rcx, gs:60h
0x180028b7a  mov     r8, rbx; P
0x180028b7d  xor     edx, edx; Flags
0x180028b7f  mov     rcx, [rcx+30h]; HeapHandle
0x180028b83  call    cs:__imp_RtlFreeHeap
0x180028b89  mov     rax, rsi
0x180028b8c  add     rsp, 38h
0x180028b90  pop     rdi
0x180028b91  pop     rsi
0x180028b92  pop     rbp
0x180028b93  pop     rbx
0x180028b94  retn
```
