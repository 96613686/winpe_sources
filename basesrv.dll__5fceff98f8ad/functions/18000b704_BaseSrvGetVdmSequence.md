# BaseSrvGetVdmSequence

- ea: `0x18000b704`
- end: `0x18000b74a`
- name: `BaseSrvGetVdmSequence`
- size: `70`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a2a0`
- `0x18000abe0`
- `0x18000c000`
- `0x18000c200`
- `0x18000c2d0`
- `0x18000c620`
- `0x18000c678`

## callees

- `0x18000b704`

## import_xrefs

- `CSRSRV!CsrUnlockProcess` at `0x18000b735`
- `CSRSRV!CsrUnlockProcess` at `0x18000b735`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b71b`
- `CSRSRV!CsrLockProcessByClientId` at `0x18000b71b`

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
0x18000b704  push    rbx
0x18000b706  sub     rsp, 20h
0x18000b70a  mov     rbx, rdx
0x18000b70d  mov     [rsp+28h+arg_10], 0
0x18000b716  lea     rdx, [rsp+28h+arg_10]
0x18000b71b  call    cs:__imp_CsrLockProcessByClientId
0x18000b722  nop     dword ptr [rax+rax+00h]
0x18000b727  test    eax, eax
0x18000b729  js      short loc_18000B743
0x18000b72b  mov     rcx, [rsp+28h+arg_10]
0x18000b730  mov     eax, [rcx+58h]
0x18000b733  mov     [rbx], eax
0x18000b735  call    cs:__imp_CsrUnlockProcess
0x18000b73c  nop     dword ptr [rax+rax+00h]
0x18000b741  xor     eax, eax
0x18000b743  add     rsp, 20h
0x18000b747  pop     rbx
0x18000b748  retn
```
