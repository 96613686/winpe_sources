# HandleVetoedOperation(ushort const *,_VETOED_OPERATION)

- ea: `0x180004aec`
- end: `0x180004c0c`
- name: `?HandleVetoedOperation@@YAKPEBGW4_VETOED_OPERATION@@@Z`
- size: `288`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800050b0`
- `0x1800050e0`
- `0x180005110`
- `0x1800054d0`
- `0x180005500`

## callees

- `0x180002c74`
- `0x180002d70`
- `0x180004aec`
- `0x180006338`
- `0x180007f1c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180004b6d`
- `KERNEL32!CloseHandle` at `0x180004b81`
- `KERNEL32!CloseHandle` at `0x180004b9d`
- `KERNEL32!CloseHandle` at `0x180004bb1`
- `KERNEL32!CloseHandle` at `0x180004b6d`
- `KERNEL32!CloseHandle` at `0x180004b81`
- `KERNEL32!CloseHandle` at `0x180004b9d`
- `KERNEL32!CloseHandle` at `0x180004bb1`
- `KERNEL32!ReadFile` at `0x180004b5f`
- `KERNEL32!ReadFile` at `0x180004b5f`
- `KERNEL32!SetEvent` at `0x180004b77`
- `KERNEL32!SetEvent` at `0x180004ba7`
- `KERNEL32!SetEvent` at `0x180004b77`
- `KERNEL32!SetEvent` at `0x180004ba7`

## pseudocode

```c
__int64 __fastcall HandleVetoedOperation(const WCHAR *a1, int a2)
{
  int v3; // ebx
  HANDLE hFile; // [rsp+30h] [rbp-40h] BYREF
  HANDLE hEvent; // [rsp+38h] [rbp-38h] BYREF
  __int128 v7; // [rsp+40h] [rbp-30h] BYREF
  __int128 v8; // [rsp+50h] [rbp-20h]
  unsigned __int64 v9; // [rsp+60h] [rbp-10h]
  unsigned int Buffer; // [rsp+90h] [rbp+20h] BYREF
  DWORD NumberOfBytesRead; // [rsp+98h] [rbp+28h] BYREF

  hFile = 0;
  hEvent = 0;
  Buffer = 0;
  v9 = 0;
  NumberOfBytesRead = 0;
  v7 = 0;
  v8 = 0;
  if ( OpenPipeAndEventHandles(a1, &hFile, &hEvent) )
  {
    if ( ReadFile(hFile, &Buffer, 4u, &NumberOfBytesRead, 0) )
    {
      v3 = DeviceCollectionBuildFromPipe(hFile, 1, (__int64)&v7);
      CloseHandle(hFile);
      SetEvent(hEvent);
      CloseHandle(hEvent);
      if ( v3 )
      {
        if ( DWORD1(v8) )
        {
          if ( a2 == 1 )
          {
            a2 = 3;
          }
          else if ( a2 == 6 )
          {
            a2 = 7;
          }
        }
        v9 = __PAIR64__(a2, Buffer);
        VetoedRemovalUI(0, (struct VETO_DEVICE_COLLECTION *)&v7);
        DeviceCollectionDestroy((struct DEVICE_COLLECTION *)&v7);
      }
    }
    else
    {
      CloseHandle(hFile);
      SetEvent(hEvent);
      CloseHandle(hEvent);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004aec  mov     [rsp-8+arg_0], rbx
0x180004af1  mov     [rsp-8+arg_8], rdi
0x180004af6  push    rbp
0x180004af7  mov     rbp, rsp
0x180004afa  sub     rsp, 70h
0x180004afe  xorps   xmm0, xmm0
0x180004b01  mov     [rbp+hFile], 0
0x180004b09  mov     edi, edx
0x180004b0b  mov     [rbp+hEvent], 0
0x180004b13  xor     eax, eax
0x180004b15  mov     [rbp+Buffer], 0
0x180004b1c  lea     rdx, [rbp+hFile]; void **
0x180004b20  mov     [rbp+var_10], rax
0x180004b24  lea     r8, [rbp+hEvent]; void **
0x180004b28  mov     [rbp+NumberOfBytesRead], 0
0x180004b2f  movups  [rbp+var_30], xmm0
0x180004b33  movups  [rbp+var_20], xmm0
0x180004b37  call    ?OpenPipeAndEventHandles@@YAHPEBGPEAPEAX1@Z; OpenPipeAndEventHandles(ushort const *,void * *,void * *)
0x180004b3c  test    eax, eax
0x180004b3e  jz      loc_180004BF5
0x180004b44  mov     rcx, [rbp+hFile]; hFile
0x180004b48  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180004b4c  mov     r8d, 4; nNumberOfBytesToRead
0x180004b52  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x180004b5b  lea     rdx, [rbp+Buffer]; lpBuffer
0x180004b5f  call    cs:__imp_ReadFile
0x180004b65  mov     rcx, [rbp+hFile]; hObject
0x180004b69  test    eax, eax
0x180004b6b  jnz     short loc_180004B89
0x180004b6d  call    cs:__imp_CloseHandle
0x180004b73  mov     rcx, [rbp+hEvent]; hEvent
0x180004b77  call    cs:__imp_SetEvent
0x180004b7d  mov     rcx, [rbp+hEvent]; hObject
0x180004b81  call    cs:__imp_CloseHandle
0x180004b87  jmp     short loc_180004BF5
0x180004b89  lea     r8, [rbp+var_30]
0x180004b8d  mov     edx, 1
0x180004b92  call    ?DeviceCollectionBuildFromPipe@@YAHPEAXW4_COLLECTION_TYPE@@PEAUDEVICE_COLLECTION@@@Z; DeviceCollectionBuildFromPipe(void *,_COLLECTION_TYPE,DEVICE_COLLECTION *)
0x180004b97  mov     rcx, [rbp+hFile]; hObject
0x180004b9b  mov     ebx, eax
0x180004b9d  call    cs:__imp_CloseHandle
0x180004ba3  mov     rcx, [rbp+hEvent]; hEvent
0x180004ba7  call    cs:__imp_SetEvent
0x180004bad  mov     rcx, [rbp+hEvent]; hObject
0x180004bb1  call    cs:__imp_CloseHandle
0x180004bb7  test    ebx, ebx
0x180004bb9  jz      short loc_180004BF5
0x180004bbb  cmp     dword ptr [rbp+var_20+4], 0
0x180004bbf  jz      short loc_180004BD8
0x180004bc1  cmp     edi, 1
0x180004bc4  jnz     short loc_180004BCD
0x180004bc6  mov     edi, 3
0x180004bcb  jmp     short loc_180004BD8
0x180004bcd  cmp     edi, 6
0x180004bd0  mov     eax, 7
0x180004bd5  cmovz   edi, eax
0x180004bd8  mov     eax, [rbp+Buffer]
0x180004bdb  lea     rdx, [rbp+var_30]; struct VETO_DEVICE_COLLECTION *
0x180004bdf  xor     ecx, ecx; hWnd
0x180004be1  mov     dword ptr [rbp+var_10], eax
0x180004be4  mov     dword ptr [rbp+var_10+4], edi
0x180004be7  call    ?VetoedRemovalUI@@YAHPEAUHWND__@@PEAUVETO_DEVICE_COLLECTION@@@Z; VetoedRemovalUI(HWND__ *,VETO_DEVICE_COLLECTION *)
0x180004bec  lea     rcx, [rbp+var_30]; struct DEVICE_COLLECTION *
0x180004bf0  call    ?DeviceCollectionDestroy@@YAXPEAUDEVICE_COLLECTION@@@Z; DeviceCollectionDestroy(DEVICE_COLLECTION *)
0x180004bf5  lea     r11, [rsp+70h+var_s0]
0x180004bfa  mov     eax, 1
0x180004bff  mov     rbx, [r11+10h]
0x180004c03  mov     rdi, [r11+18h]
0x180004c07  mov     rsp, r11
0x180004c0a  pop     rbp
0x180004c0b  retn
```
