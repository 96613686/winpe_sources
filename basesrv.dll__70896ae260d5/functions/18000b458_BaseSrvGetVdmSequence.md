# BaseSrvGetVdmSequence

- ea: `0x18000b458`
- end: `0x18000b49b`
- name: `BaseSrvGetVdmSequence`
- size: `67`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180009fc0`
- `0x18000a960`
- `0x18000bd20`
- `0x18000be80`
- `0x18000bf40`
- `0x18000c250`
- `0x18000c2a4`

## callees

- `0x18000b458`

## import_xrefs

- `CSRSRV!CsrUnlockProcess` at `0x18000b486`
- `CSRSRV!CsrUnlockProcess` at `0x18000b486`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b46c`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b46c`

## pseudocode

```c
__int64 __fastcall BaseSrvGetVdmSequence(__int64 a1, _DWORD *a2)
{
  __int64 result; // rax
  __int64 v4; // rcx
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF

  v5 = 0;
  result = CsrLockProcessByClientId(a1, &v5);
  if ( (int)result >= 0 )
  {
    v4 = v5;
    *a2 = *(_DWORD *)(v5 + 88);
    CsrUnlockProcess(v4);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b458  push    rbx
0x18000b45a  sub     rsp, 20h
0x18000b45e  and     [rsp+28h+arg_10], 0
0x18000b464  mov     rbx, rdx
0x18000b467  lea     rdx, [rsp+28h+arg_10]
0x18000b46c  call    cs:__imp_CsrLockProcessByClientId
0x18000b473  nop     dword ptr [rax+rax+00h]
0x18000b478  test    eax, eax
0x18000b47a  js      short loc_18000B494
0x18000b47c  mov     rcx, [rsp+28h+arg_10]
0x18000b481  mov     eax, [rcx+58h]
0x18000b484  mov     [rbx], eax
0x18000b486  call    cs:__imp_CsrUnlockProcess
0x18000b48d  nop     dword ptr [rax+rax+00h]
0x18000b492  xor     eax, eax
0x18000b494  add     rsp, 20h
0x18000b498  pop     rbx
0x18000b499  retn
```
