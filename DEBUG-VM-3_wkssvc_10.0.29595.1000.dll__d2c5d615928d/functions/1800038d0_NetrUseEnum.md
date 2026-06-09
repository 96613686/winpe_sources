# NetrUseEnum

- ea: `0x1800038d0`
- end: `0x180003b5e`
- name: `NetrUseEnum`
- size: `654`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002a60`
- `0x1800031d0`
- `0x1800038d0`
- `0x1800051c0`
- `0x18001e420`

## import_xrefs

- `ntdll!RtlAcquireResourceShared` at `0x180003a09`
- `ntdll!RtlAcquireResourceShared` at `0x180003a09`
- `ntdll!RtlCopyLuid` at `0x1800039a5`
- `ntdll!RtlCopyLuid` at `0x1800039a5`
- `ntdll!RtlReleaseResource` at `0x180003ac3`
- `ntdll!RtlReleaseResource` at `0x180003ac3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ab6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ab6`

## pseudocode

```c
__int64 __fastcall NetrUseEnum(__int64 a1, __int64 a2, unsigned int a3, _DWORD *a4, __int64 a5)
{
  __int64 v8; // rsi
  int v9; // r14d
  DWORD v10; // r15d
  int v11; // ecx
  __int64 v12; // rax
  __int64 result; // rax
  unsigned int v14; // ebx
  __int64 i; // rax
  __int64 v16; // rcx
  __int64 *v17; // r8
  unsigned int v18; // ebx
  struct _LUID SourceLuid; // [rsp+50h] [rbp-88h] BYREF
  __int64 v20; // [rsp+58h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-78h] BYREF
  __int64 v22; // [rsp+68h] [rbp-70h] BYREF
  __int64 v23; // [rsp+70h] [rbp-68h]
  struct _LUID DestinationLuid[2]; // [rsp+78h] [rbp-60h] BYREF
  __int128 v25; // [rsp+88h] [rbp-50h]
  int v26; // [rsp+98h] [rbp-40h]

  v23 = a5;
  SourceLuid = 0;
  *(_OWORD *)&DestinationLuid[0].LowPart = 0;
  v25 = 0;
  v26 = 0;
  hMem = 0;
  v8 = 0;
  v22 = 0;
  v9 = 0;
  LODWORD(v20) = 0;
  v10 = (unsigned __int16)*(_DWORD *)a2;
  if ( v10 > 3 )
    return 124;
  v11 = *(_DWORD *)a2 & 0x10000;
  v12 = *(_QWORD *)(a2 + 8);
  if ( !v12 )
    return 87;
  *(_QWORD *)(v12 + 8) = 0;
  **(_DWORD **)(a2 + 8) = 0;
  if ( v11 )
  {
    SourceLuid = (struct _LUID)-1LL;
  }
  else
  {
    result = WsImpersonateAndGetLogonId(&SourceLuid);
    if ( (_DWORD)result )
      return result;
  }
  DestinationLuid[0].LowPart = 1;
  DestinationLuid[0].HighPart = 6;
  RtlCopyLuid((PLUID)&DestinationLuid[1].HighPart, &SourceLuid);
  DestinationLuid[1].LowPart = v10;
  v26 = 0;
  result = WsDeviceControlGetInfo(0, WsRedirDeviceHandle, 1311143, DestinationLuid, 36, &hMem, -1, 0);
  if ( !(_DWORD)result )
  {
    v14 = DWORD2(v25);
    if ( RtlAcquireResourceShared(&Resource, 1u) )
    {
      for ( i = 0; (unsigned int)i < dword_18004F110; i = (unsigned int)(i + 1) )
      {
        v16 = Use + 24 * i;
        if ( SourceLuid.LowPart == *(_DWORD *)(v16 + 8) && SourceLuid.HighPart == *(_DWORD *)(v16 + 12)
          || SourceLuid.LowPart == *(_DWORD *)(v16 + 16) && SourceLuid.HighPart == *(_DWORD *)(v16 + 20) )
        {
          v17 = *(__int64 **)v16;
          goto LABEL_14;
        }
      }
      v17 = 0;
LABEL_14:
      if ( v14 || v17 )
      {
        v18 = WsEnumUseInfo(
                &SourceLuid,
                v10,
                v17,
                (unsigned __int16 *)hMem,
                v14,
                (HLOCAL *)&v22,
                a3,
                &v20,
                a4,
                (int *)v23);
        v8 = v22;
        v9 = v20;
      }
      else
      {
        *a4 = 0;
        v18 = 0;
      }
    }
    else
    {
      v18 = 2140;
    }
    LocalFree(hMem);
    RtlReleaseResource(&Resource);
    *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) = v8;
    **(_DWORD **)(a2 + 8) = v9;
    return v18;
  }
  return result;
}

```

## disassembly

```asm
0x1800038d0  mov     r11, rsp
0x1800038d3  mov     [r11+8], rbx
0x1800038d7  mov     [r11+18h], rsi
0x1800038db  push    rdi
0x1800038dc  push    r12
0x1800038de  push    r13
0x1800038e0  push    r14
0x1800038e2  push    r15
0x1800038e4  sub     rsp, 0B0h
0x1800038eb  mov     rax, cs:__security_cookie
0x1800038f2  xor     rax, rsp
0x1800038f5  mov     [rsp+0D8h+var_38], rax
0x1800038fd  mov     r12, r9
0x180003900  mov     r13d, r8d
0x180003903  mov     rdi, rdx
0x180003906  mov     rax, [rsp+0D8h+arg_20]
0x18000390e  mov     [rsp+0D8h+var_68], rax
0x180003913  xor     ebx, ebx
0x180003915  mov     qword ptr [rsp+0D8h+SourceLuid.LowPart], rbx
0x18000391a  xorps   xmm0, xmm0
0x18000391d  xor     eax, eax
0x18000391f  movups  xmmword ptr [rsp+0D8h+DestinationLuid.LowPart], xmm0
0x180003924  movups  xmmword ptr [r11-50h], xmm0
0x180003929  mov     [r11-40h], eax
0x18000392d  mov     [r11-78h], rbx
0x180003931  mov     esi, ebx
0x180003933  mov     [r11-70h], rbx
0x180003937  mov     r14d, ebx
0x18000393a  mov     dword ptr [rsp+0D8h+var_80], ebx
0x18000393e  mov     ecx, [rdx]
0x180003940  movzx   r15d, cx
0x180003944  cmp     r15d, 3
0x180003948  ja      loc_180003B4D
0x18000394e  and     ecx, 10000h
0x180003954  mov     rax, [rdx+8]
0x180003958  test    rax, rax
0x18000395b  jz      loc_180003B54
0x180003961  mov     [rax+8], rbx
0x180003965  mov     rax, [rdx+8]
0x180003969  mov     [rax], ebx
0x18000396b  jmp     short loc_180003977
0x18000396d  mov     eax, 57h ; 'W'
0x180003972  jmp     loc_180003ADA
0x180003977  test    ecx, ecx
0x180003979  jz      loc_180003B20
0x18000397f  mov     qword ptr [rsp+0D8h+SourceLuid.LowPart], 0FFFFFFFFFFFFFFFFh
0x180003988  mov     [rsp+0D8h+DestinationLuid.LowPart], 1
0x180003990  mov     [rsp+0D8h+DestinationLuid.HighPart], 6
0x180003998  lea     rdx, [rsp+0D8h+SourceLuid]; SourceLuid
0x18000399d  lea     rcx, [rsp+0D8h+DestinationLuid.HighPart+8]; DestinationLuid
0x1800039a5  call    cs:__imp_RtlCopyLuid
0x1800039ab  mov     [rsp+0D8h+DestinationLuid.LowPart+8], r15d
0x1800039b3  mov     [rsp+0D8h+var_40], ebx
0x1800039ba  mov     dword ptr [rsp+0D8h+var_A0], ebx
0x1800039be  mov     [rsp+0D8h+var_A8], 0FFFFFFFFh
0x1800039c6  lea     rax, [rsp+0D8h+hMem]
0x1800039cb  mov     [rsp+0D8h+var_B0], rax
0x1800039d0  mov     [rsp+0D8h+var_B8], 24h ; '$'
0x1800039d8  lea     r9, [rsp+0D8h+DestinationLuid]
0x1800039dd  mov     r8d, 1401A7h
0x1800039e3  mov     rdx, cs:WsRedirDeviceHandle
0x1800039ea  xor     ecx, ecx
0x1800039ec  call    WsDeviceControlGetInfo
0x1800039f1  test    eax, eax
0x1800039f3  jnz     loc_180003ADA
0x1800039f9  mov     ebx, [rsp+0D8h+var_48]
0x180003a00  mov     dl, 1; Wait
0x180003a02  lea     rcx, Resource; Resource
0x180003a09  call    cs:__imp_RtlAcquireResourceShared
0x180003a0f  test    al, al
0x180003a11  jz      loc_180003B34
0x180003a17  xor     eax, eax
0x180003a19  mov     r11d, [rsp+0D8h+SourceLuid.HighPart]
0x180003a1e  mov     r9d, [rsp+0D8h+SourceLuid.LowPart]
0x180003a23  mov     r8d, cs:dword_18004F110
0x180003a2a  mov     r10, cs:Use
0x180003a31  cmp     eax, r8d
0x180003a34  jnb     loc_180003B18
0x180003a3a  lea     rdx, [rax+rax*2]
0x180003a3e  lea     rcx, [r10+rdx*8]
0x180003a42  cmp     r9d, [rcx+8]
0x180003a46  jz      short loc_180003A56
0x180003a48  cmp     r9d, [rcx+10h]
0x180003a4c  jz      loc_180003B3E
0x180003a52  inc     eax
0x180003a54  jmp     short loc_180003A31
0x180003a56  cmp     r11d, [rcx+0Ch]
0x180003a5a  jnz     short loc_180003A48
0x180003a5c  mov     r8, [rcx]
0x180003a5f  test    ebx, ebx
0x180003a61  jz      loc_180003B07
0x180003a67  mov     rax, [rsp+0D8h+var_68]
0x180003a6c  mov     [rsp+0D8h+var_90], rax; __int64
0x180003a71  mov     [rsp+0D8h+var_98], r12; __int64
0x180003a76  lea     rax, [rsp+0D8h+var_80]
0x180003a7b  mov     [rsp+0D8h+var_A0], rax; __int64
0x180003a80  mov     [rsp+0D8h+var_A8], r13d; int
0x180003a85  lea     rax, [rsp+0D8h+var_70]
0x180003a8a  mov     [rsp+0D8h+var_B0], rax; __int64
0x180003a8f  mov     [rsp+0D8h+var_B8], ebx; int
0x180003a93  mov     r9, [rsp+0D8h+hMem]
0x180003a98  mov     edx, r15d
0x180003a9b  lea     rcx, [rsp+0D8h+SourceLuid]; SourceLuid
0x180003aa0  call    WsEnumUseInfo
0x180003aa5  mov     ebx, eax
0x180003aa7  mov     rsi, [rsp+0D8h+var_70]
0x180003aac  mov     r14d, dword ptr [rsp+0D8h+var_80]
0x180003ab1  mov     rcx, [rsp+0D8h+hMem]; hMem
0x180003ab6  call    cs:__imp_LocalFree
0x180003abc  lea     rcx, Resource; Resource
0x180003ac3  call    cs:__imp_RtlReleaseResource
0x180003ac9  mov     rcx, [rdi+8]
0x180003acd  mov     [rcx+8], rsi
0x180003ad1  mov     rcx, [rdi+8]
0x180003ad5  mov     [rcx], r14d
0x180003ad8  mov     eax, ebx
0x180003ada  mov     rcx, [rsp+0D8h+var_38]
0x180003ae2  xor     rcx, rsp; StackCookie
0x180003ae5  call    __security_check_cookie
0x180003aea  lea     r11, [rsp+0D8h+var_28]
0x180003af2  mov     rbx, [r11+30h]
0x180003af6  mov     rsi, [r11+40h]
0x180003afa  mov     rsp, r11
0x180003afd  pop     r15
0x180003aff  pop     r14
0x180003b01  pop     r13
0x180003b03  pop     r12
0x180003b05  pop     rdi
0x180003b06  retn
0x180003b07  test    r8, r8
0x180003b0a  jnz     loc_180003A67
0x180003b10  mov     [r12], r8d
0x180003b14  xor     ebx, ebx
0x180003b16  jmp     short loc_180003AB1
0x180003b18  xor     r8d, r8d
0x180003b1b  jmp     loc_180003A5F
0x180003b20  lea     rcx, [rsp+0D8h+SourceLuid]; DestinationLuid
0x180003b25  call    WsImpersonateAndGetLogonId
0x180003b2a  test    eax, eax
0x180003b2c  jz      loc_180003988
0x180003b32  jmp     short loc_180003ADA
0x180003b34  mov     ebx, 85Ch
0x180003b39  jmp     loc_180003AB1
0x180003b3e  cmp     r11d, [rcx+14h]
0x180003b42  jnz     loc_180003A52
0x180003b48  jmp     loc_180003A5C
0x180003b4d  mov     eax, 7Ch ; '|'
0x180003b52  jmp     short loc_180003ADA
0x180003b54  mov     eax, 57h ; 'W'
0x180003b59  jmp     loc_180003ADA
```
