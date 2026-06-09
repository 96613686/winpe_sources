# USBD_UrbAllocate

- ea: `0x14000d370`
- end: `0x14000d557`
- name: `USBD_UrbAllocate`
- size: `487`
- prototype: `NTSTATUS __stdcall(USBD_HANDLE USBDHandle, PURB *Urb)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001154`
- `0x14000762c`

## callees

- `0x14000d370`
- `0x14000d830`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d536`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d536`
- `ntoskrnl!DbgPrintEx` at `0x14000d39a`
- `ntoskrnl!DbgPrintEx` at `0x14000d3d3`
- `ntoskrnl!DbgPrintEx` at `0x14000d425`
- `ntoskrnl!DbgPrintEx` at `0x14000d452`
- `ntoskrnl!DbgPrintEx` at `0x14000d4b9`
- `ntoskrnl!DbgPrintEx` at `0x14000d510`
- `ntoskrnl!DbgPrintEx` at `0x14000d39a`
- `ntoskrnl!DbgPrintEx` at `0x14000d3d3`
- `ntoskrnl!DbgPrintEx` at `0x14000d425`
- `ntoskrnl!DbgPrintEx` at `0x14000d452`
- `ntoskrnl!DbgPrintEx` at `0x14000d4b9`
- `ntoskrnl!DbgPrintEx` at `0x14000d510`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d491`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000d491`

## string_xrefs

- `0x14000d503`: `UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n`
- `0x14000d3fb`: `UsbdHandleInfo->PendingDelete is set, UsbdHandleInfo 0x%p\n`

## pseudocode

```c
NTSTATUS __stdcall USBD_UrbAllocate(USBD_HANDLE USBDHandle, PURB *Urb)
{
  NTSTATUS v4; // edi
  __int64 (__fastcall *v5)(_QWORD); // rax
  struct _URB *PoolWithTag; // rax
  void (__fastcall *v7)(_QWORD); // rax

  if ( USBDHandle )
  {
    if ( !Urb )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Urb cant be NULL\n");
      return -1073741811;
    }
    if ( *((_BYTE *)USBDHandle + 225) )
    {
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete is set, UsbdHandleInfo 0x%p\n", USBDHandle);
    }
    else
    {
      if ( *((int *)USBDHandle + 55) >= 1 )
      {
        _InterlockedIncrement((volatile signed __int32 *)USBDHandle + 55);
        v5 = (__int64 (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 15);
        if ( v5 )
        {
          v4 = v5(*((_QWORD *)USBDHandle + 6));
        }
        else
        {
          PoolWithTag = (struct _URB *)ExAllocatePoolWithTag(PoolType, 0x98u, *((_DWORD *)USBDHandle + 16));
          *Urb = PoolWithTag;
          if ( PoolWithTag )
          {
            memset(PoolWithTag, 0, sizeof(struct _URB));
            v4 = 0;
          }
          else
          {
            if ( g_EnableDbgPrints )
              DbgPrintEx(0x4Du, 0, "Insufficient Memory to allocate URB\n");
            v4 = -1073741670;
          }
        }
        if ( v4 < 0 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)USBDHandle + 55, 0xFFFFFFFF) <= 1 )
          {
            if ( *((_BYTE *)USBDHandle + 225) )
            {
              v7 = (void (__fastcall *)(_QWORD))*((_QWORD *)USBDHandle + 14);
              if ( v7 )
                v7(*((_QWORD *)USBDHandle + 6));
              ExFreePoolWithTag(USBDHandle, *((_DWORD *)USBDHandle + 16));
            }
            else if ( g_EnableDbgPrints )
            {
              DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->PendingDelete should be set here UsbdHandleInfo 0x%p\n", USBDHandle);
            }
          }
          goto LABEL_33;
        }
        return v4;
      }
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "UsbdHandleInfo->ReferenceCount must be 1 or higher 0x%p\n", USBDHandle);
    }
    v4 = -1073741436;
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "USBDInternal_ReferenceHandle failed %x\n", -1073741436);
    goto LABEL_33;
  }
  if ( g_EnableDbgPrints )
    DbgPrintEx(0x4Du, 0, "USBDHandle cant be NULL\n");
  v4 = -1073741811;
  if ( Urb )
LABEL_33:
    *Urb = 0;
  return v4;
}

```

## disassembly

```asm
0x14000d370  push    rbx
0x14000d372  push    rdi
0x14000d373  push    r14
0x14000d375  push    r15
0x14000d377  sub     rsp, 28h
0x14000d37b  mov     r14, rdx
0x14000d37e  mov     rbx, rcx
0x14000d381  test    rcx, rcx
0x14000d384  jnz     short loc_14000D3B9
0x14000d386  cmp     cs:g_EnableDbgPrints, cl
0x14000d38c  jz      short loc_14000D3A6
0x14000d38e  lea     r8, aUsbdhandleCant; "USBDHandle cant be NULL\n"
0x14000d395  xor     edx, edx; Level
0x14000d397  lea     ecx, [rbx+4Dh]; ComponentId
0x14000d39a  call    cs:__imp_DbgPrintEx
0x14000d3a1  nop     dword ptr [rax+rax+00h]
0x14000d3a6  mov     edi, 0C000000Dh
0x14000d3ab  test    r14, r14
0x14000d3ae  jz      loc_14000D549
0x14000d3b4  jmp     loc_14000D542
0x14000d3b9  test    r14, r14
0x14000d3bc  jnz     short loc_14000D3E9
0x14000d3be  cmp     cs:g_EnableDbgPrints, r14b
0x14000d3c5  jz      short loc_14000D3DF
0x14000d3c7  xor     edx, edx; Level
0x14000d3c9  lea     r8, aUrbCantBeNull; "Urb cant be NULL\n"
0x14000d3d0  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d3d3  call    cs:__imp_DbgPrintEx
0x14000d3da  nop     dword ptr [rax+rax+00h]
0x14000d3df  mov     edi, 0C000000Dh
0x14000d3e4  jmp     loc_14000D549
0x14000d3e9  cmp     byte ptr [rcx+0E1h], 0
0x14000d3f0  jz      short loc_14000D404
0x14000d3f2  cmp     cs:g_EnableDbgPrints, 0
0x14000d3f9  jz      short loc_14000D431
0x14000d3fb  lea     r8, aUsbdhandleinfo_0; "UsbdHandleInfo->PendingDelete is set, U"...
0x14000d402  jmp     short loc_14000D41D
0x14000d404  cmp     dword ptr [rcx+0DCh], 1
0x14000d40b  jge     short loc_14000D463
0x14000d40d  cmp     cs:g_EnableDbgPrints, 0
0x14000d414  jz      short loc_14000D431
0x14000d416  lea     r8, aUsbdhandleinfo; "UsbdHandleInfo->ReferenceCount must be "...
0x14000d41d  xor     edx, edx; Level
0x14000d41f  mov     r9, rbx
0x14000d422  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d425  call    cs:__imp_DbgPrintEx
0x14000d42c  nop     dword ptr [rax+rax+00h]
0x14000d431  cmp     cs:g_EnableDbgPrints, 0
0x14000d438  mov     edi, 0C0000184h
0x14000d43d  jz      loc_14000D542
0x14000d443  xor     edx, edx; Level
0x14000d445  lea     r8, aUsbdinternalRe; "USBDInternal_ReferenceHandle failed %x"...
0x14000d44c  mov     r9d, edi
0x14000d44f  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d452  call    cs:__imp_DbgPrintEx
0x14000d459  nop     dword ptr [rax+rax+00h]
0x14000d45e  jmp     loc_14000D542
0x14000d463  lock inc dword ptr [rcx+0DCh]
0x14000d46a  mov     rax, [rcx+78h]
0x14000d46e  test    rax, rax
0x14000d471  jz      short loc_14000D480
0x14000d473  mov     rcx, [rcx+30h]
0x14000d477  call    _guard_dispatch_icall
0x14000d47c  mov     edi, eax
0x14000d47e  jmp     short loc_14000D4DB
0x14000d480  mov     r8d, [rcx+40h]; Tag
0x14000d484  mov     edi, 98h
0x14000d489  mov     ecx, cs:PoolType; PoolType
0x14000d48f  mov     edx, edi; NumberOfBytes
0x14000d491  call    cs:__imp_ExAllocatePoolWithTag
0x14000d498  nop     dword ptr [rax+rax+00h]
0x14000d49d  mov     [r14], rax
0x14000d4a0  test    rax, rax
0x14000d4a3  jnz     short loc_14000D4CC
0x14000d4a5  cmp     cs:g_EnableDbgPrints, al
0x14000d4ab  jz      short loc_14000D4C5
0x14000d4ad  lea     r8, aInsufficientMe; "Insufficient Memory to allocate URB\n"
0x14000d4b4  xor     edx, edx; Level
0x14000d4b6  lea     ecx, [rdi-4Bh]; ComponentId
0x14000d4b9  call    cs:__imp_DbgPrintEx
0x14000d4c0  nop     dword ptr [rax+rax+00h]
0x14000d4c5  mov     edi, 0C000009Ah
0x14000d4ca  jmp     short loc_14000D4DB
0x14000d4cc  mov     r8, rdi; Size
0x14000d4cf  xor     edx, edx; Val
0x14000d4d1  mov     rcx, rax; void *
0x14000d4d4  call    memset
0x14000d4d9  xor     edi, edi
0x14000d4db  test    edi, edi
0x14000d4dd  jns     short loc_14000D549
0x14000d4df  or      eax, 0FFFFFFFFh
0x14000d4e2  lock xadd [rbx+0DCh], eax
0x14000d4ea  sub     eax, 1
0x14000d4ed  jg      short loc_14000D542
0x14000d4ef  cmp     byte ptr [rbx+0E1h], 0
0x14000d4f6  jnz     short loc_14000D51E
0x14000d4f8  cmp     cs:g_EnableDbgPrints, 0
0x14000d4ff  jz      short loc_14000D542
0x14000d501  xor     edx, edx; Level
0x14000d503  lea     r8, aUsbdhandleinfo_1; "UsbdHandleInfo->PendingDelete should be"...
0x14000d50a  mov     r9, rbx
0x14000d50d  lea     ecx, [rdx+4Dh]; ComponentId
0x14000d510  call    cs:__imp_DbgPrintEx
0x14000d517  nop     dword ptr [rax+rax+00h]
0x14000d51c  jmp     short loc_14000D542
0x14000d51e  mov     rax, [rbx+70h]
0x14000d522  test    rax, rax
0x14000d525  jz      short loc_14000D530
0x14000d527  mov     rcx, [rbx+30h]
0x14000d52b  call    _guard_dispatch_icall
0x14000d530  mov     edx, [rbx+40h]; Tag
0x14000d533  mov     rcx, rbx; P
0x14000d536  call    cs:__imp_ExFreePoolWithTag
0x14000d53d  nop     dword ptr [rax+rax+00h]
0x14000d542  mov     qword ptr [r14], 0
0x14000d549  mov     eax, edi
0x14000d54b  add     rsp, 28h
0x14000d54f  pop     r15
0x14000d551  pop     r14
0x14000d553  pop     rdi
0x14000d554  pop     rbx
0x14000d555  retn
```
