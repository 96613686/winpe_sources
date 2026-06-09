# HttpCreateClientStream

- ea: `0x180005c70`
- end: `0x180005d57`
- name: `HttpCreateClientStream`
- size: `231`
- prototype: `__int64 __fastcall(HANDLE FileHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180002b40`
- `0x180005c70`
- `0x18000a5f0`
- `0x18000b0b8`
- `0x18000b0f0`

## pseudocode

```c
__int64 __fastcall HttpCreateClientStream(HANDLE FileHandle, __int64 a2, int a3, _QWORD *a4)
{
  ULONG v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v12; // [rsp+40h] [rbp-58h] BYREF
  __int128 InputBuffer; // [rsp+48h] [rbp-50h] BYREF
  __int128 v14; // [rsp+58h] [rbp-40h] BYREF

  LODWORD(v12) = 0;
  InputBuffer = 0;
  v14 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_Id(FileHandle, 32, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, a2, a3);
  if ( a4 )
  {
    *a4 = 0;
    *(_QWORD *)&InputBuffer = a2;
    DWORD2(InputBuffer) = a3;
    v8 = HttpApiSynchronousDeviceControl(FileHandle, 0x1240C0u, &InputBuffer, 0x10u, &v14, 0x10u, &v12);
    if ( !v8 )
    {
      v10 = v14;
      *a4 = v14;
      if ( (byte_1800126A3 & 4) != 0 )
        WPP_SF_I(v9, 33, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, v10);
    }
  }
  else
  {
    return 87;
  }
  return v8;
}

```

## disassembly

```asm
0x180005c70  push    rbx
0x180005c72  push    rbp
0x180005c73  push    rsi
0x180005c74  push    rdi
0x180005c75  sub     rsp, 78h
0x180005c79  mov     rax, cs:__security_cookie
0x180005c80  xor     rax, rsp
0x180005c83  mov     [rsp+98h+var_30], rax
0x180005c88  xorps   xmm0, xmm0
0x180005c8b  mov     dword ptr [rsp+98h+var_58], 0
0x180005c93  xorps   xmm1, xmm1
0x180005c96  mov     rdi, r9
0x180005c99  movups  [rsp+98h+InputBuffer], xmm0
0x180005c9e  mov     esi, r8d
0x180005ca1  mov     rbx, rdx
0x180005ca4  movups  [rsp+98h+var_40], xmm1
0x180005ca9  mov     rbp, rcx
0x180005cac  test    cs:byte_1800126A3, 4
0x180005cb3  jz      short loc_180005CCE
0x180005cb5  mov     dword ptr [rsp+98h+var_78], r8d
0x180005cba  mov     edx, 20h ; ' '
0x180005cbf  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x180005cc6  mov     r9, rbx
0x180005cc9  call    WPP_SF_Id
0x180005cce  test    rdi, rdi
0x180005cd1  jnz     short loc_180005CD8
0x180005cd3  lea     ebx, [rdi+57h]
0x180005cd6  jmp     short loc_180005D3F
0x180005cd8  lea     rax, [rsp+98h+var_58]
0x180005cdd  mov     qword ptr [rdi], 0
0x180005ce4  mov     [rsp+98h+var_68], rax; __int64
0x180005ce9  lea     r8, [rsp+98h+InputBuffer]; InputBuffer
0x180005cee  mov     r9d, 10h; InputBufferLength
0x180005cf4  mov     qword ptr [rsp+98h+InputBuffer], rbx
0x180005cf9  lea     rax, [rsp+98h+var_40]
0x180005cfe  mov     [rsp+98h+var_70], r9d; ULONG
0x180005d03  mov     edx, 1240C0h; IoControlCode
0x180005d08  mov     [rsp+98h+var_78], rax; PVOID
0x180005d0d  mov     rcx, rbp; FileHandle
0x180005d10  mov     dword ptr [rsp+98h+InputBuffer+8], esi
0x180005d14  call    HttpApiSynchronousDeviceControl
0x180005d19  mov     ebx, eax
0x180005d1b  test    eax, eax
0x180005d1d  jnz     short loc_180005D3F
0x180005d1f  mov     r9, qword ptr [rsp+98h+var_40]
0x180005d24  mov     [rdi], r9
0x180005d27  test    cs:byte_1800126A3, 4
0x180005d2e  jz      short loc_180005D3F
0x180005d30  lea     edx, [rax+21h]
0x180005d33  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x180005d3a  call    WPP_SF_I
0x180005d3f  mov     eax, ebx
0x180005d41  mov     rcx, [rsp+98h+var_30]
0x180005d46  xor     rcx, rsp; StackCookie
0x180005d49  call    __security_check_cookie
0x180005d4e  add     rsp, 78h
0x180005d52  pop     rdi
0x180005d53  pop     rsi
0x180005d54  pop     rbp
0x180005d55  pop     rbx
0x180005d56  retn
```
