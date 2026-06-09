# SuGetTask(_GUID *,_GUID *,_SU_TASK_OBJECT * *)

- ea: `0x1400198d4`
- end: `0x1400199cd`
- name: `?SuGetTask@@YAHPEAU_GUID@@0PEAPEAU_SU_TASK_OBJECT@@@Z`
- size: `249`
- prototype: `__int64 __fastcall(struct _GUID *, struct _GUID *, struct _SU_TASK_OBJECT **)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140015524`
- `0x1400198a0`

## callees

- `0x1400198d4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140019982`
- `KERNEL32!LocalFree` at `0x140019995`
- `KERNEL32!LocalFree` at `0x140019982`
- `KERNEL32!LocalFree` at `0x140019995`
- `KERNEL32!SetLastError` at `0x14001998a`
- `KERNEL32!SetLastError` at `0x1400199b6`
- `KERNEL32!SetLastError` at `0x14001998a`
- `KERNEL32!SetLastError` at `0x1400199b6`
- `KERNEL32!GetLastError` at `0x14001996f`
- `KERNEL32!GetLastError` at `0x14001996f`
- `KERNEL32!DeviceIoControl` at `0x140019963`
- `KERNEL32!DeviceIoControl` at `0x140019963`
- `KERNEL32!LocalAlloc` at `0x140019904`
- `KERNEL32!LocalAlloc` at `0x140019904`

## pseudocode

```c
__int64 __fastcall SuGetTask(struct _GUID *a1, struct _GUID *a2, struct _SU_TASK_OBJECT **a3)
{
  DWORD nOutBufferSize; // edi
  char *v7; // rax
  char *v8; // rbx
  _OWORD *v9; // rsi
  unsigned int v10; // edi
  __int128 v11; // xmm1
  DWORD BytesReturned; // [rsp+90h] [rbp+18h] BYREF

  BytesReturned = 0;
  *a3 = 0;
  nOutBufferSize = 4720;
  while ( 1 )
  {
    v7 = (char *)LocalAlloc(0, nOutBufferSize + 72);
    v8 = v7;
    if ( !v7 )
      break;
    v9 = v7 + 40;
    *(struct _GUID *)(v7 + 40) = *a1;
    *(struct _GUID *)(v7 + 56) = *a2;
    v10 = DeviceIoControl(Spaceport, 0xE70C08u, v7 + 40, 0x20u, v7 + 72, nOutBufferSize, &BytesReturned, 0);
    if ( v10 )
    {
      v11 = *((_OWORD *)v8 + 6);
      *v9 = *((_OWORD *)v8 + 5);
      v9[1] = v11;
      *a3 = (struct _SU_TASK_OBJECT *)v8;
      return v10;
    }
    if ( GetLastError() != 234 )
    {
      LocalFree(v8);
      return v10;
    }
    nOutBufferSize = *((_DWORD *)v8 + 19);
    LocalFree(v8);
    SetLastError(0);
  }
  SetLastError(0x5AAu);
  return 0;
}

```

## disassembly

```asm
0x1400198d4  mov     rax, rsp
0x1400198d7  push    rbx
0x1400198d8  push    rbp
0x1400198d9  push    rsi
0x1400198da  push    rdi
0x1400198db  push    r14
0x1400198dd  push    r15
0x1400198df  sub     rsp, 48h
0x1400198e3  mov     r14, r8
0x1400198e6  mov     dword ptr [rax+18h], 0
0x1400198ed  mov     rbp, rdx
0x1400198f0  mov     qword ptr [r8], 0
0x1400198f7  mov     r15, rcx
0x1400198fa  mov     edi, 1270h
0x1400198ff  lea     edx, [rdi+48h]; uBytes
0x140019902  xor     ecx, ecx; uFlags
0x140019904  call    cs:__imp_LocalAlloc
0x14001990a  mov     rbx, rax
0x14001990d  test    rax, rax
0x140019910  jz      loc_1400199B1
0x140019916  movups  xmm0, xmmword ptr [r15]
0x14001991a  lea     rsi, [rax+28h]
0x14001991e  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x140019927  lea     rcx, [rax+48h]
0x14001992b  mov     r9d, 20h ; ' '; nInBufferSize
0x140019931  movdqu  xmmword ptr [rsi], xmm0
0x140019935  mov     r8, rsi; lpInBuffer
0x140019938  mov     edx, 0E70C08h; dwIoControlCode
0x14001993d  movups  xmm1, xmmword ptr [rbp+0]
0x140019941  movdqu  xmmword ptr [rax+38h], xmm1
0x140019946  lea     rax, [rsp+78h+BytesReturned]
0x14001994e  mov     [rsp+78h+lpBytesReturned], rax; lpBytesReturned
0x140019953  mov     [rsp+78h+nOutBufferSize], edi; nOutBufferSize
0x140019957  mov     [rsp+78h+lpOutBuffer], rcx; lpOutBuffer
0x14001995c  mov     rcx, cs:?Spaceport@@3PEAXEA; hDevice
0x140019963  call    cs:__imp_DeviceIoControl
0x140019969  mov     edi, eax
0x14001996b  test    eax, eax
0x14001996d  jnz     short loc_14001999D
0x14001996f  call    cs:__imp_GetLastError
0x140019975  mov     rcx, rbx; hMem
0x140019978  cmp     eax, 0EAh
0x14001997d  jnz     short loc_140019995
0x14001997f  mov     edi, [rbx+4Ch]
0x140019982  call    cs:__imp_LocalFree
0x140019988  xor     ecx, ecx; dwErrCode
0x14001998a  call    cs:__imp_SetLastError
0x140019990  jmp     loc_1400198FF
0x140019995  call    cs:__imp_LocalFree
0x14001999b  jmp     short loc_1400199BE
0x14001999d  movups  xmm0, xmmword ptr [rbx+50h]
0x1400199a1  movups  xmm1, xmmword ptr [rbx+60h]
0x1400199a5  movups  xmmword ptr [rsi], xmm0
0x1400199a8  movups  xmmword ptr [rsi+10h], xmm1
0x1400199ac  mov     [r14], rbx
0x1400199af  jmp     short loc_1400199BE
0x1400199b1  mov     ecx, 5AAh; dwErrCode
0x1400199b6  call    cs:__imp_SetLastError
0x1400199bc  xor     edi, edi
0x1400199be  mov     eax, edi
0x1400199c0  add     rsp, 48h
0x1400199c4  pop     r15
0x1400199c6  pop     r14
0x1400199c8  pop     rdi
0x1400199c9  pop     rsi
0x1400199ca  pop     rbp
0x1400199cb  pop     rbx
0x1400199cc  retn
```
