# GetUserTokenFromContext

- ea: `0x180005880`
- end: `0x1800058c2`
- name: `GetUserTokenFromContext`
- size: `66`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024c4`
- `0x180005880`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800058ab`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1800058ab`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromContext(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax

  *a2 = 0;
  if ( !a1 )
    return 0;
  if ( !(unsigned __int8)IsUMgrQueryUserContextPresent() )
    return 0;
  result = UMgrQueryUserToken(a1, a2);
  if ( (int)result >= 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x180005880  mov     [rsp+arg_0], rbx
0x180005885  push    rdi
0x180005886  sub     rsp, 20h
0x18000588a  mov     qword ptr [rdx], 0
0x180005891  mov     rbx, rdx
0x180005894  mov     rdi, rcx
0x180005897  test    rcx, rcx
0x18000589a  jz      short loc_1800058B5
0x18000589c  call    IsUMgrQueryUserContextPresent
0x1800058a1  test    al, al
0x1800058a3  jz      short loc_1800058B5
0x1800058a5  mov     rdx, rbx
0x1800058a8  mov     rcx, rdi
0x1800058ab  call    cs:__imp_UMgrQueryUserToken
0x1800058b1  test    eax, eax
0x1800058b3  js      short loc_1800058B7
0x1800058b5  xor     eax, eax
0x1800058b7  mov     rbx, [rsp+28h+arg_0]
0x1800058bc  add     rsp, 20h
0x1800058c0  pop     rdi
0x1800058c1  retn
```
