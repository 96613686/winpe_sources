# CCredentialProviderSerialization::GetSerialization(ulong *,uchar * *)

- ea: `0x14000dcf0`
- end: `0x14000dd7e`
- name: `?GetSerialization@CCredentialProviderSerialization@@UEAAJPEAKPEAPEAE@Z`
- size: `142`
- prototype: `__int64 __fastcall(const void **this, unsigned int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008904`
- `0x14000dcf0`
- `0x14001e060`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000dd1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000dd1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000dd27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000dd27`

## pseudocode

```c
__int64 __fastcall CCredentialProviderSerialization::GetSerialization(
        const void **this,
        unsigned int *a2,
        unsigned __int8 **a3)
{
  void *v6; // rsi
  unsigned int v7; // ebx
  void *v9; // [rsp+40h] [rbp+8h] BYREF

  *a2 = 0;
  *a3 = 0;
  v6 = CoTaskMemAlloc(*((unsigned int *)this + 18));
  CoTaskMemFree(0);
  v9 = v6;
  if ( v6 )
  {
    v7 = 0;
    memcpy_0(v6, this[8], *((unsigned int *)this + 18));
    *a3 = (unsigned __int8 *)v6;
    *a2 = *((_DWORD *)this + 18);
    v9 = 0;
  }
  else
  {
    v7 = -2147024882;
  }
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v9);
  return v7;
}

```

## disassembly

```asm
0x14000dcf0  mov     [rsp+arg_8], rbx
0x14000dcf5  mov     [rsp+arg_10], rsi
0x14000dcfa  push    rdi
0x14000dcfb  push    r14
0x14000dcfd  push    r15
0x14000dcff  sub     rsp, 20h
0x14000dd03  mov     dword ptr [rdx], 0
0x14000dd09  mov     rdi, rcx
0x14000dd0c  mov     qword ptr [r8], 0
0x14000dd13  mov     r14, r8
0x14000dd16  mov     ecx, [rcx+48h]; cb
0x14000dd19  mov     r15, rdx
0x14000dd1c  call    cs:__imp_CoTaskMemAlloc
0x14000dd22  xor     ecx, ecx; pv
0x14000dd24  mov     rsi, rax
0x14000dd27  call    cs:__imp_CoTaskMemFree
0x14000dd2d  mov     [rsp+38h+arg_0], rsi
0x14000dd32  test    rsi, rsi
0x14000dd35  jz      short loc_14000DD59
0x14000dd37  mov     r8d, [rdi+48h]; Size
0x14000dd3b  xor     ebx, ebx
0x14000dd3d  mov     rdx, [rdi+40h]; Src
0x14000dd41  mov     rcx, rsi; void *
0x14000dd44  call    memcpy_0
0x14000dd49  mov     [r14], rsi
0x14000dd4c  mov     eax, [rdi+48h]
0x14000dd4f  mov     [r15], eax
0x14000dd52  mov     [rsp+38h+arg_0], rbx
0x14000dd57  jmp     short loc_14000DD5E
0x14000dd59  mov     ebx, 8007000Eh
0x14000dd5e  lea     rcx, [rsp+38h+arg_0]
0x14000dd63  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x14000dd68  mov     rsi, [rsp+38h+arg_10]
0x14000dd6d  mov     eax, ebx
0x14000dd6f  mov     rbx, [rsp+38h+arg_8]
0x14000dd74  add     rsp, 20h
0x14000dd78  pop     r15
0x14000dd7a  pop     r14
0x14000dd7c  pop     rdi
0x14000dd7d  retn
```
