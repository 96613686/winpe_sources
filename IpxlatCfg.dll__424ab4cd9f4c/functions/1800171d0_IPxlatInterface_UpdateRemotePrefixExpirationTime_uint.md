# IPxlatInterface::UpdateRemotePrefixExpirationTime(uint)

- ea: `0x1800171d0`
- end: `0x18001729c`
- name: `?UpdateRemotePrefixExpirationTime@IPxlatInterface@@AEAAXI@Z`
- size: `204`
- prototype: `void __fastcall(IPxlatInterface *this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001468c`
- `0x180016094`

## callees

- `0x180001d40`
- `0x18000c224`
- `0x1800171d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800171ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800171ee`

## pseudocode

```c
void __fastcall IPxlatInterface::UpdateRemotePrefixExpirationTime(IPxlatInterface *this, int a2)
{
  __int64 v4; // rcx
  ULONGLONG v5; // r8
  int v6; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v7[16]; // [rsp+38h] [rbp-40h] BYREF
  const char *v8; // [rsp+48h] [rbp-30h]
  __int64 v9; // [rsp+50h] [rbp-28h]
  int *v10; // [rsp+58h] [rbp-20h]
  __int64 v11; // [rsp+60h] [rbp-18h]

  v5 = GetTickCount64() / 0x3E8;
  if ( (int)v5 + a2 < (unsigned int)v5 )
  {
    *((_DWORD *)this + 51) = -1;
    if ( (Microsoft_Windows_IPxlatCfgEnableBits & 1) != 0 )
    {
      v6 = 534;
      v8 = "Overflow calculating remote prefix expiration time.";
      v9 = 52;
      v10 = &v6;
      v11 = 4;
      McGenEventWrite_EventWriteTransfer(v4, IPXLATCFG_ERROR_EVENT, v5, 3, v7);
    }
  }
  else
  {
    *((_DWORD *)this + 51) = v5 + a2;
  }
}

```

## disassembly

```asm
0x1800171d0  mov     [rsp+arg_8], rbx
0x1800171d5  push    rdi
0x1800171d6  sub     rsp, 70h
0x1800171da  mov     rax, cs:__security_cookie
0x1800171e1  xor     rax, rsp
0x1800171e4  mov     [rsp+78h+var_10], rax
0x1800171e9  mov     ebx, edx
0x1800171eb  mov     rdi, rcx
0x1800171ee  call    cs:__imp_GetTickCount64
0x1800171f4  mov     r8, rax
0x1800171f7  mov     rax, 624DD2F1A9FBE77h
0x180017201  mul     r8
0x180017204  sub     r8, rdx
0x180017207  shr     r8, 1
0x18001720a  add     r8, rdx
0x18001720d  shr     r8, 9
0x180017211  lea     eax, [r8+rbx]
0x180017215  cmp     eax, r8d
0x180017218  jb      short loc_180017222
0x18001721a  mov     [rdi+0CCh], eax
0x180017220  jmp     short loc_180017281
0x180017222  mov     dword ptr [rdi+0CCh], 0FFFFFFFFh
0x18001722c  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, 1
0x180017233  jz      short loc_180017281
0x180017235  lea     rax, aOverflowCalcul; "Overflow calculating remote prefix expi"...
0x18001723c  mov     [rsp+78h+var_48], 216h
0x180017244  mov     [rsp+78h+var_30], rax
0x180017249  lea     rdx, IPXLATCFG_ERROR_EVENT
0x180017250  lea     rax, [rsp+78h+var_48]
0x180017255  mov     [rsp+78h+var_28], 34h ; '4'
0x18001725e  mov     [rsp+78h+var_20], rax
0x180017263  mov     r9d, 3
0x180017269  lea     rax, [rsp+78h+var_40]
0x18001726e  mov     [rsp+78h+var_18], 4
0x180017277  mov     [rsp+78h+var_58], rax
0x18001727c  call    McGenEventWrite_EventWriteTransfer
0x180017281  mov     rcx, [rsp+78h+var_10]
0x180017286  xor     rcx, rsp; StackCookie
0x180017289  call    __security_check_cookie
0x18001728e  mov     rbx, [rsp+78h+arg_8]
0x180017296  add     rsp, 70h
0x18001729a  pop     rdi
0x18001729b  retn
```
