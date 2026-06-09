# HttpGetExtension

- ea: `0x18000a3c0`
- end: `0x18000a472`
- name: `HttpGetExtension`
- size: `178`
- prototype: `ULONG __stdcall(HTTPAPI_VERSION Version, ULONG Extension, PVOID Buffer, ULONG BufferSize)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x180004010`
- `0x18000a3c0`
- `0x18000b080`
- `0x18000b584`

## pseudocode

```c
ULONG __stdcall HttpGetExtension(HTTPAPI_VERSION Version, ULONG Extension, PVOID Buffer, ULONG BufferSize)
{
  ULONG v7; // ebx

  if ( (byte_1800126A3 & 0x20) != 0 )
    WPP_SF_llqL(
      1053,
      Extension,
      WPP_d7d37be12c843e04b49fe410409f6e6f_Traceguids,
      Version.HttpApiMajorVersion,
      Version.HttpApiMinorVersion,
      Buffer,
      BufferSize);
  if ( (unsigned int)HttpIsInitialized(0) )
  {
    if ( Extension == 2203 && BufferSize == 8 && Buffer )
    {
      v7 = 0;
      *(_QWORD *)Buffer = &off_18000E010;
    }
    else
    {
      v7 = 87;
    }
  }
  else
  {
    v7 = 1114;
  }
  if ( (byte_1800126A3 & 0x20) != 0 )
    WPP_SF_d(1053, 11, WPP_d7d37be12c843e04b49fe410409f6e6f_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18000a3c0  mov     [rsp+arg_0], rbx
0x18000a3c5  mov     [rsp+arg_8], rsi
0x18000a3ca  push    rdi
0x18000a3cb  sub     rsp, 40h
0x18000a3cf  mov     ebx, r9d
0x18000a3d2  mov     rdi, r8
0x18000a3d5  mov     esi, edx
0x18000a3d7  test    cs:byte_1800126A3, 20h
0x18000a3de  jz      short loc_18000A407
0x18000a3e0  mov     eax, ecx
0x18000a3e2  mov     [rsp+48h+var_18], ebx
0x18000a3e6  mov     [rsp+48h+var_20], r8
0x18000a3eb  lea     r8, WPP_d7d37be12c843e04b49fe410409f6e6f_Traceguids
0x18000a3f2  shr     eax, 10h
0x18000a3f5  movzx   r9d, cx
0x18000a3f9  mov     ecx, 41Dh
0x18000a3fe  mov     [rsp+48h+var_28], eax
0x18000a402  call    WPP_SF_llqL
0x18000a407  xor     ecx, ecx
0x18000a409  call    HttpIsInitialized
0x18000a40e  test    eax, eax
0x18000a410  jnz     short loc_18000A419
0x18000a412  mov     ebx, 45Ah
0x18000a417  jmp     short loc_18000A43E
0x18000a419  cmp     esi, 89Bh
0x18000a41f  jnz     short loc_18000A439
0x18000a421  cmp     ebx, 8
0x18000a424  jnz     short loc_18000A439
0x18000a426  test    rdi, rdi
0x18000a429  jz      short loc_18000A439
0x18000a42b  lea     rax, off_18000E010
0x18000a432  xor     ebx, ebx
0x18000a434  mov     [rdi], rax
0x18000a437  jmp     short loc_18000A43E
0x18000a439  mov     ebx, 57h ; 'W'
0x18000a43e  test    cs:byte_1800126A3, 20h
0x18000a445  jz      short loc_18000A460
0x18000a447  mov     edx, 0Bh
0x18000a44c  lea     r8, WPP_d7d37be12c843e04b49fe410409f6e6f_Traceguids
0x18000a453  mov     ecx, 41Dh
0x18000a458  mov     r9d, ebx
0x18000a45b  call    WPP_SF_d
0x18000a460  mov     rsi, [rsp+48h+arg_8]
0x18000a465  mov     eax, ebx
0x18000a467  mov     rbx, [rsp+48h+arg_0]
0x18000a46c  add     rsp, 40h
0x18000a470  pop     rdi
0x18000a471  retn
```
