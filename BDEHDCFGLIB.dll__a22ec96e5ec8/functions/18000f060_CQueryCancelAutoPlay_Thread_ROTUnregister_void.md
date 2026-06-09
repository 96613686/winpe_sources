# CQueryCancelAutoPlay::Thread_ROTUnregister(void *)

- ea: `0x18000f060`
- end: `0x18000f0c3`
- name: `?Thread_ROTUnregister@CQueryCancelAutoPlay@@CAIPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000f060`
- `0x180015010`

## import_xrefs

- `ole32!CoInitializeEx` at `0x18000f076`
- `ole32!CoInitializeEx` at `0x18000f076`
- `ole32!GetRunningObjectTable` at `0x18000f087`
- `ole32!GetRunningObjectTable` at `0x18000f087`
- `ole32!CoUninitialize` at `0x18000f0b5`
- `ole32!CoUninitialize` at `0x18000f0b5`

## pseudocode

```c
__int64 __fastcall CQueryCancelAutoPlay::Thread_ROTUnregister(void *a1)
{
  unsigned int v1; // ebx
  LPRUNNINGOBJECTTABLE pprot; // [rsp+30h] [rbp+8h] BYREF

  v1 = (unsigned int)a1;
  pprot = 0;
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    if ( GetRunningObjectTable(0, &pprot) >= 0 )
    {
      ((void (__fastcall *)(LPRUNNINGOBJECTTABLE, _QWORD))pprot->lpVtbl->Revoke)(pprot, v1);
      ((void (__fastcall *)(LPRUNNINGOBJECTTABLE))pprot->lpVtbl->Release)(pprot);
    }
    CoUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x18000f060  push    rbx
0x18000f062  sub     rsp, 20h
0x18000f066  mov     rbx, rcx
0x18000f069  mov     [rsp+28h+pprot], 0
0x18000f072  xor     ecx, ecx; pvReserved
0x18000f074  xor     edx, edx; dwCoInit
0x18000f076  call    cs:__imp_CoInitializeEx
0x18000f07c  test    eax, eax
0x18000f07e  js      short loc_18000F0BB
0x18000f080  lea     rdx, [rsp+28h+pprot]; pprot
0x18000f085  xor     ecx, ecx; reserved
0x18000f087  call    cs:__imp_GetRunningObjectTable
0x18000f08d  test    eax, eax
0x18000f08f  js      short loc_18000F0B5
0x18000f091  mov     rcx, [rsp+28h+pprot]
0x18000f096  mov     edx, ebx
0x18000f098  mov     rax, [rcx]
0x18000f09b  mov     rax, [rax+20h]
0x18000f09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a4  mov     rcx, [rsp+28h+pprot]
0x18000f0a9  mov     rax, [rcx]
0x18000f0ac  mov     rax, [rax+10h]
0x18000f0b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0b5  call    cs:__imp_CoUninitialize
0x18000f0bb  xor     eax, eax
0x18000f0bd  add     rsp, 20h
0x18000f0c1  pop     rbx
0x18000f0c2  retn
```
