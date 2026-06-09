# VidSidServiceCheck

- ea: `0x1400769d8`
- end: `0x140076af9`
- name: `VidSidServiceCheck`
- size: `289`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140082818`
- `0x1400829a0`
- `0x140082a18`
- `0x140082aac`
- `0x140082c38`
- `0x14008d52c`
- `0x14008db0c`
- `0x1400a18c0`
- `0x1400b0880`
- `0x1400b0a44`

## callees

- `0x140021c60`
- `0x140021e00`
- `0x1400768e0`
- `0x1400769d8`
- `0x14009b92c`
- `0x14009b9ec`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140076acd`
- `ntoskrnl!ZwClose` at `0x140076acd`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140076a2b`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140076a2b`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140076a60`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140076a9b`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140076a60`
- `ntoskrnl!RtlCheckTokenMembership` at `0x140076a9b`

## pseudocode

```c
__int64 VidSidServiceCheck()
{
  NTSTATUS v0; // ebx
  _BYTE v2[4]; // [rsp+20h] [rbp-19h] BYREF
  int v3; // [rsp+24h] [rbp-15h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-11h] BYREF
  _BYTE v5[80]; // [rsp+30h] [rbp-9h] BYREF

  TokenHandle = 0;
  v2[0] = 0;
  memset(v5, 0, 0x44u);
  v3 = 68;
  v0 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &TokenHandle);
  if ( v0 >= 0 )
  {
    v0 = VidSidInitializeVmCompute(v5, &v3);
    if ( v0 >= 0 )
    {
      v0 = RtlCheckTokenMembership(TokenHandle, v5, v2);
      if ( v0 >= 0 )
      {
        if ( v2[0] )
        {
LABEL_5:
          v0 = 0;
          goto LABEL_10;
        }
        v0 = VidSidpInitializeVmms(v5, &v3);
        if ( v0 >= 0 )
        {
          v0 = RtlCheckTokenMembership(TokenHandle, v5, v2);
          if ( v0 >= 0 )
          {
            if ( v2[0] )
              goto LABEL_5;
            v0 = (unsigned int)VidCurrentProcessIsAdmin() == 0 ? 0xC000000D : 0;
          }
        }
      }
    }
  }
LABEL_10:
  if ( TokenHandle )
    ZwClose(TokenHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x1400769d8  mov     [rsp-8+arg_0], rbx
0x1400769dd  push    rbp
0x1400769de  lea     rbp, [rsp-57h]
0x1400769e3  sub     rsp, 90h
0x1400769ea  mov     rax, cs:__security_cookie
0x1400769f1  xor     rax, rsp
0x1400769f4  mov     [rbp+57h+var_10], rax
0x1400769f8  mov     ebx, 44h ; 'D'
0x1400769fd  mov     [rbp+57h+TokenHandle], 0
0x140076a05  mov     r8d, ebx; Size
0x140076a08  mov     [rbp+57h+var_70], 0
0x140076a0c  xor     edx, edx; Val
0x140076a0e  lea     rcx, [rbp+57h+var_60]; void *
0x140076a12  call    memset
0x140076a17  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140076a1b  mov     [rbp+57h+var_6C], ebx
0x140076a1e  lea     edx, [rbx-3Ch]; DesiredAccess
0x140076a21  mov     r8d, 200h; HandleAttributes
0x140076a27  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140076a2b  call    cs:__imp_ZwOpenProcessTokenEx
0x140076a32  nop     dword ptr [rax+rax+00h]
0x140076a37  mov     ebx, eax
0x140076a39  test    eax, eax
0x140076a3b  js      loc_140076AC4
0x140076a41  lea     rdx, [rbp+57h+var_6C]
0x140076a45  lea     rcx, [rbp+57h+var_60]
0x140076a49  call    VidSidInitializeVmCompute
0x140076a4e  mov     ebx, eax
0x140076a50  test    eax, eax
0x140076a52  js      short loc_140076AC4
0x140076a54  mov     rcx, [rbp+57h+TokenHandle]
0x140076a58  lea     r8, [rbp+57h+var_70]
0x140076a5c  lea     rdx, [rbp+57h+var_60]
0x140076a60  call    cs:__imp_RtlCheckTokenMembership
0x140076a67  nop     dword ptr [rax+rax+00h]
0x140076a6c  mov     ebx, eax
0x140076a6e  test    eax, eax
0x140076a70  js      short loc_140076AC4
0x140076a72  cmp     [rbp+57h+var_70], 0
0x140076a76  jz      short loc_140076A7C
0x140076a78  xor     ebx, ebx
0x140076a7a  jmp     short loc_140076AC4
0x140076a7c  lea     rdx, [rbp+57h+var_6C]
0x140076a80  lea     rcx, [rbp+57h+var_60]
0x140076a84  call    VidSidpInitializeVmms
0x140076a89  mov     ebx, eax
0x140076a8b  test    eax, eax
0x140076a8d  js      short loc_140076AC4
0x140076a8f  mov     rcx, [rbp+57h+TokenHandle]
0x140076a93  lea     r8, [rbp+57h+var_70]
0x140076a97  lea     rdx, [rbp+57h+var_60]
0x140076a9b  call    cs:__imp_RtlCheckTokenMembership
0x140076aa2  nop     dword ptr [rax+rax+00h]
0x140076aa7  mov     ebx, eax
0x140076aa9  test    eax, eax
0x140076aab  js      short loc_140076AC4
0x140076aad  cmp     [rbp+57h+var_70], 0
0x140076ab1  jnz     short loc_140076A78
0x140076ab3  call    VidCurrentProcessIsAdmin
0x140076ab8  neg     eax
0x140076aba  sbb     ebx, ebx
0x140076abc  not     ebx
0x140076abe  and     ebx, 0C000000Dh
0x140076ac4  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x140076ac8  test    rcx, rcx
0x140076acb  jz      short loc_140076AD9
0x140076acd  call    cs:__imp_ZwClose
0x140076ad4  nop     dword ptr [rax+rax+00h]
0x140076ad9  mov     eax, ebx
0x140076adb  mov     rcx, [rbp+57h+var_10]
0x140076adf  xor     rcx, rsp; StackCookie
0x140076ae2  call    __security_check_cookie
0x140076ae7  mov     rbx, [rsp+90h+arg_0]
0x140076aef  add     rsp, 90h
0x140076af6  pop     rbp
0x140076af7  retn
```
