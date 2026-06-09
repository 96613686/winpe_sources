# BaseSrvRegisterThread

- ea: `0x180006000`
- end: `0x18000615f`
- name: `BaseSrvRegisterThread`
- size: `351`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006000`

## import_xrefs

- `ntdll!NtClose` at `0x180006140`
- `ntdll!NtClose` at `0x180006140`
- `ntdll!NtDuplicateObject` at `0x18000609b`
- `ntdll!NtDuplicateObject` at `0x18000609b`
- `CSRSRV!CsrUnlockThread` at `0x18000611a`
- `CSRSRV!CsrUnlockThread` at `0x18000611a`
- `CSRSRV!CsrLockThreadByClientId` at `0x1800060f5`
- `CSRSRV!CsrLockThreadByClientId` at `0x1800060f5`
- `CSRSRV!CsrUnlockProcess` at `0x1800060d6`
- `CSRSRV!CsrUnlockProcess` at `0x180006151`
- `CSRSRV!CsrUnlockProcess` at `0x1800060d6`
- `CSRSRV!CsrUnlockProcess` at `0x180006151`
- `CSRSRV!CsrCreateThread` at `0x1800060bf`
- `CSRSRV!CsrCreateThread` at `0x1800060bf`
- `CSRSRV!CsrLockProcessByClientId` at `0x180006056`
- `CSRSRV!CsrLockProcessByClientId` at `0x180006056`

## pseudocode

```c
__int64 __fastcall BaseSrvRegisterThread(__int64 a1)
{
  struct _TEB *v1; // rdi
  __int128 v2; // rax
  __int64 result; // rax
  NTSTATUS v4; // ebx
  __int128 v5; // [rsp+40h] [rbp-18h] BYREF
  __int64 v6; // [rsp+60h] [rbp+8h] BYREF
  void *TargetHandle; // [rsp+70h] [rbp+18h] BYREF
  void *v8; // [rsp+78h] [rbp+20h] BYREF

  v5 = 0;
  v6 = 0;
  v8 = 0;
  TargetHandle = 0;
  v1 = NtCurrentTeb();
  v2 = *(_OWORD *)(a1 + 72);
  v5 = v2;
  if ( *(_OWORD *)&v1->ClientId != v2 )
    return 3221225485LL;
  result = CsrLockProcessByClientId(v2, &v6);
  if ( (int)result >= 0 && v6 )
  {
    v4 = NtDuplicateObject(
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           (HANDLE)0xFFFFFFFFFFFFFFFELL,
           (HANDLE)0xFFFFFFFFFFFFFFFFLL,
           &TargetHandle,
           0x1FFFFFu,
           0,
           0);
    if ( v4 >= 0 && (v4 = CsrCreateThread(v6, TargetHandle, &v5, 0), v4 < 0) )
    {
      NtClose(TargetHandle);
      CsrUnlockProcess(v6);
    }
    else
    {
      CsrUnlockProcess(v6);
      if ( v4 >= 0 )
      {
        v4 = CsrLockThreadByClientId(*((_QWORD *)&v5 + 1), v5, &v8);
        if ( v4 >= 0 )
        {
          if ( v8 )
          {
            v1->CsrClientThread = v8;
            CsrUnlockThread(v8);
          }
        }
      }
    }
    return (unsigned int)v4;
  }
  return result;
}

```

## disassembly

```asm
0x180006000  mov     r11, rsp
0x180006003  mov     [r11+10h], rbx
0x180006007  push    rdi
0x180006008  sub     rsp, 50h
0x18000600c  xor     ebx, ebx
0x18000600e  xorps   xmm0, xmm0
0x180006011  movups  [rsp+58h+var_18], xmm0
0x180006016  mov     [r11+8], rbx
0x18000601a  mov     [r11+20h], rbx
0x18000601e  mov     [r11+18h], rbx
0x180006022  mov     rdi, gs:30h
0x18000602b  mov     rax, [rcx+48h]
0x18000602f  mov     rdx, [rcx+50h]
0x180006033  mov     [r11-18h], rax
0x180006037  mov     [r11-10h], rdx
0x18000603b  cmp     [rdi+40h], rax
0x18000603f  jnz     loc_180006134
0x180006045  cmp     [rdi+48h], rdx
0x180006049  jnz     loc_180006134
0x18000604f  lea     rdx, [r11+8]
0x180006053  mov     rcx, rax
0x180006056  call    cs:__imp_CsrLockProcessByClientId
0x18000605d  nop     dword ptr [rax+rax+00h]
0x180006062  test    eax, eax
0x180006064  js      loc_180006128
0x18000606a  cmp     [rsp+58h+arg_0], rbx
0x18000606f  jz      loc_180006128
0x180006075  mov     rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x18000607c  mov     [rsp+58h+Options], ebx; Options
0x180006080  mov     r8, rcx; TargetProcessHandle
0x180006083  mov     [rsp+58h+HandleAttributes], ebx; HandleAttributes
0x180006087  lea     r9, [rsp+58h+TargetHandle]; TargetHandle
0x18000608c  mov     [rsp+58h+DesiredAccess], 1FFFFFh; DesiredAccess
0x180006094  mov     rdx, 0FFFFFFFFFFFFFFFEh; SourceHandle
0x18000609b  call    cs:__imp_NtDuplicateObject
0x1800060a2  nop     dword ptr [rax+rax+00h]
0x1800060a7  mov     ebx, eax
0x1800060a9  test    eax, eax
0x1800060ab  js      short loc_1800060D1
0x1800060ad  mov     rdx, [rsp+58h+TargetHandle]
0x1800060b2  lea     r8, [rsp+58h+var_18]
0x1800060b7  mov     rcx, [rsp+58h+arg_0]
0x1800060bc  xor     r9d, r9d
0x1800060bf  call    cs:__imp_CsrCreateThread
0x1800060c6  nop     dword ptr [rax+rax+00h]
0x1800060cb  mov     ebx, eax
0x1800060cd  test    eax, eax
0x1800060cf  js      short loc_18000613B
0x1800060d1  mov     rcx, [rsp+58h+arg_0]
0x1800060d6  call    cs:__imp_CsrUnlockProcess
0x1800060dd  nop     dword ptr [rax+rax+00h]
0x1800060e2  test    ebx, ebx
0x1800060e4  js      short loc_180006126
0x1800060e6  mov     rdx, qword ptr [rsp+58h+var_18]
0x1800060eb  lea     r8, [rsp+58h+arg_18]
0x1800060f0  mov     rcx, qword ptr [rsp+58h+var_18+8]
0x1800060f5  call    cs:__imp_CsrLockThreadByClientId
0x1800060fc  nop     dword ptr [rax+rax+00h]
0x180006101  mov     ebx, eax
0x180006103  test    eax, eax
0x180006105  js      short loc_180006126
0x180006107  mov     rax, [rsp+58h+arg_18]
0x18000610c  test    rax, rax
0x18000610f  jz      short loc_180006126
0x180006111  mov     [rdi+70h], rax
0x180006115  mov     rcx, [rsp+58h+arg_18]
0x18000611a  call    cs:__imp_CsrUnlockThread
0x180006121  nop     dword ptr [rax+rax+00h]
0x180006126  mov     eax, ebx
0x180006128  mov     rbx, [rsp+58h+arg_8]
0x18000612d  add     rsp, 50h
0x180006131  pop     rdi
0x180006132  retn
0x180006134  mov     eax, 0C000000Dh
0x180006139  jmp     short loc_180006128
0x18000613b  mov     rcx, [rsp+58h+TargetHandle]; Handle
0x180006140  call    cs:__imp_NtClose
0x180006147  nop     dword ptr [rax+rax+00h]
0x18000614c  mov     rcx, [rsp+58h+arg_0]
0x180006151  call    cs:__imp_CsrUnlockProcess
0x180006158  nop     dword ptr [rax+rax+00h]
0x18000615d  jmp     short loc_180006126
```
