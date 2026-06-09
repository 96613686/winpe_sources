# VfsPreRedirect

- ea: `0x14000ade0`
- end: `0x14000ae5b`
- name: `VfsPreRedirect`
- size: `123`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA Data)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140001530`
- `0x140007f84`
- `0x140008038`
- `0x14000ab10`
- `0x14000ad40`

## callees

- `0x14000ade0`
- `0x14000b11c`
- `0x14000f124`

## pseudocode

```c
__int64 __fastcall VfsPreRedirect(PFLT_CALLBACK_DATA Data, __int64 a2)
{
  __int64 result; // rax
  NTSTATUS v4; // eax
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF
  __int64 v6; // [rsp+48h] [rbp+20h] BYREF

  v5 = 0;
  if ( !VfsDecodeFileObject(*(_QWORD *)(a2 + 32), &v6, &v5) )
    return 1;
  if ( ((Data->Iopb->MajorFunction + 17) & 0xFB) == 0 && (*(_DWORD *)(v5 + 4) & 4) != 0 )
    return 3;
  v4 = VfsRedirectIo(Data);
  if ( v4 >= 0 )
    return 1;
  Data->IoStatus.Status = v4;
  result = 4;
  Data->IoStatus.Information = 0;
  return result;
}

```

## disassembly

```asm
0x14000ade0  push    rbx
0x14000ade2  sub     rsp, 20h
0x14000ade6  mov     rax, rdx
0x14000ade9  mov     [rsp+28h+arg_8], 0
0x14000adf2  mov     rbx, rcx
0x14000adf5  lea     r8, [rsp+28h+arg_8]
0x14000adfa  lea     rdx, [rsp+28h+arg_18]
0x14000adff  mov     rcx, [rax+20h]
0x14000ae03  call    VfsDecodeFileObject
0x14000ae08  test    al, al
0x14000ae0a  jz      short loc_14000AE4F
0x14000ae0c  mov     rax, [rbx+10h]
0x14000ae10  mov     rcx, [rsp+28h+arg_8]
0x14000ae15  mov     dl, [rax+4]
0x14000ae18  add     dl, 11h
0x14000ae1b  test    dl, 0FBh
0x14000ae1e  jnz     short loc_14000AE2E
0x14000ae20  mov     eax, [rcx+4]
0x14000ae23  test    al, 4
0x14000ae25  jz      short loc_14000AE2E
0x14000ae27  mov     eax, 3
0x14000ae2c  jmp     short loc_14000AE54
0x14000ae2e  mov     rdx, rcx
0x14000ae31  mov     rcx, rbx; Data
0x14000ae34  call    VfsRedirectIo
0x14000ae39  test    eax, eax
0x14000ae3b  jns     short loc_14000AE4F
0x14000ae3d  mov     [rbx+18h], eax
0x14000ae40  mov     eax, 4
0x14000ae45  mov     qword ptr [rbx+20h], 0
0x14000ae4d  jmp     short loc_14000AE54
0x14000ae4f  mov     eax, 1
0x14000ae54  add     rsp, 20h
0x14000ae58  pop     rbx
0x14000ae59  retn
```
