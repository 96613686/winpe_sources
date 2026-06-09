# IsIgdQualified(ushort *)

- ea: `0x18000f190`
- end: `0x18000f494`
- name: `?IsIgdQualified@@YAHPEAG@Z`
- size: `772`
- prototype: `__int64 __fastcall(LPWSTR AddressString)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000eadc`

## callees

- `0x18000a644`
- `0x18000a66c`
- `0x18000a778`
- `0x18000b97c`
- `0x18000f190`
- `0x1800137f6`
- `0x180013802`
- `0x18001380e`
- `0x180013840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18000f277`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f441`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f441`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000f265`
- `IPHLPAPI!GetAdaptersAddresses` at `0x18000f265`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x18000f2e1`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x18000f370`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x18000f2e1`
- `IPHLPAPI!ResolveIpNetEntry2` at `0x18000f370`

## pseudocode

```c
__int64 __fastcall IsIgdQualified(LPWSTR AddressString)
{
  _QWORD *v2; // rdi
  unsigned int v3; // r12d
  IP_ADAPTER_ADDRESSES_LH *v4; // rbx
  signed int AdaptersAddresses; // eax
  bool v6; // sf
  size_t v7; // r8
  NTSTATUS v8; // eax
  signed int v9; // edi
  IP_ADAPTER_ADDRESSES_LH *v10; // r15
  PIP_ADAPTER_GATEWAY_ADDRESS_LH i; // r14
  size_t iSockaddrLength; // r8
  NTSTATUS v13; // eax
  signed int v14; // esi
  _QWORD *v15; // rdi
  ULONG SizePointer; // [rsp+30h] [rbp-D0h] BYREF
  int v18[3]; // [rsp+34h] [rbp-CCh] BYREF
  _MIB_IPNET_ROW2 Row; // [rsp+40h] [rbp-C0h] BYREF
  struct _MIB_IPNET_ROW2 Buf1; // [rsp+A0h] [rbp-60h] BYREF
  struct sockaddr Src[8]; // [rsp+100h] [rbp+0h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v3 = 0;
  SizePointer = 0;
  v4 = 0;
  memset_0(Src, 0, sizeof(Src));
  v18[0] = 0;
  Row.Address.Ipv4.sin_family = 0;
  memset_0(&Row.Address.Ipv6.sin6_port, 0, 0x56u);
  if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
    WPP_SF_S(v2[2], 55, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids, AddressString);
  while ( 1 )
  {
    AdaptersAddresses = GetAdaptersAddresses(0, 0x80u, 0, v4, &SizePointer);
    if ( AdaptersAddresses != 111 )
      break;
    v4 = (IP_ADAPTER_ADDRESSES_LH *)CoTaskMemRealloc(v4, SizePointer);
    if ( !v4 )
      goto LABEL_45;
  }
  v6 = AdaptersAddresses < 0;
  if ( AdaptersAddresses > 0 )
    v6 = 1;
  if ( !v6 && (int)IpStringToSockAddress(AddressString, Src, v18) >= 0 )
  {
    v7 = v18[0];
    if ( (unsigned __int64)v18[0] > 0x1C )
      v7 = 28;
    memcpy_0(&Row, Src, v7);
    v8 = ResolveIpNetEntry2(&Row, 0);
    v9 = v8;
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
    if ( v9 >= 0 )
    {
      v10 = v4;
      if ( v4 )
      {
        while ( 2 )
        {
          Buf1.Address.Ipv4.sin_family = 0;
          memset_0(&Buf1.Address.Ipv6.sin6_port, 0, 0x56u);
          for ( i = v10->FirstGatewayAddress; i; i = i->Next )
          {
            iSockaddrLength = i->Address.iSockaddrLength;
            if ( iSockaddrLength > 0x1C )
              iSockaddrLength = 28;
            memcpy_0(&Buf1, i->Address.lpSockaddr, iSockaddrLength);
            v13 = ResolveIpNetEntry2(&Buf1, 0);
            v14 = v13;
            if ( v13 > 0 )
              v14 = (unsigned __int16)v13 | 0x80070000;
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
              v15 = WPP_GLOBAL_Control;
            }
            if ( v14 >= 0 )
            {
              if ( Buf1.PhysicalAddressLength == Row.PhysicalAddressLength
                && !memcmp_0(Buf1.PhysicalAddress, Row.PhysicalAddress, Row.PhysicalAddressLength) )
              {
                if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
                  WPP_SF_(v15[2], 58, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
                v3 = 1;
                goto LABEL_45;
              }
              if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
                WPP_SF_(v15[2], 59, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
            }
          }
          v10 = v10->Next;
          if ( v10 )
            continue;
          break;
        }
      }
    }
  }
LABEL_45:
  CoTaskMemFree(v4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x18000f190  push    rbp
0x18000f192  push    rbx
0x18000f193  push    rsi
0x18000f194  push    rdi
0x18000f195  push    r12
0x18000f197  push    r13
0x18000f199  push    r14
0x18000f19b  push    r15
0x18000f19d  lea     rbp, [rsp-98h]
0x18000f1a5  sub     rsp, 198h
0x18000f1ac  mov     rax, cs:__security_cookie
0x18000f1b3  xor     rax, rsp
0x18000f1b6  mov     [rbp+0D0h+var_50], rax
0x18000f1bd  mov     rsi, rcx
0x18000f1c0  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f1c7  lea     r13, WPP_GLOBAL_Control
0x18000f1ce  cmp     rdi, r13
0x18000f1d1  jz      short loc_18000F1F5
0x18000f1d3  test    byte ptr [rdi+1Ch], 20h
0x18000f1d7  jz      short loc_18000F1F5
0x18000f1d9  mov     rcx, [rdi+10h]
0x18000f1dd  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f1e4  mov     edx, 36h ; '6'
0x18000f1e9  call    WPP_SF_
0x18000f1ee  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f1f5  mov     r14d, 80h
0x18000f1fb  lea     rcx, [rbp+0D0h+Src]; void *
0x18000f1ff  xor     r12d, r12d
0x18000f202  mov     r8d, r14d; Size
0x18000f205  xor     edx, edx; Val
0x18000f207  mov     [rsp+1D0h+var_1A0], r12d
0x18000f20c  xor     ebx, ebx
0x18000f20e  call    memset_0
0x18000f213  xor     eax, eax
0x18000f215  mov     [rsp+1D0h+var_19C], ebx
0x18000f219  xor     edx, edx; Val
0x18000f21b  mov     word ptr [rsp+1D0h+Row.Address], ax
0x18000f220  lea     r8d, [r12+56h]; Size
0x18000f225  lea     rcx, [rsp+1D0h+Row.Address+2]; void *
0x18000f22a  call    memset_0
0x18000f22f  cmp     rdi, r13
0x18000f232  jz      short loc_18000F250
0x18000f234  test    byte ptr [rdi+1Ch], 8
0x18000f238  jz      short loc_18000F250
0x18000f23a  mov     rcx, [rdi+10h]
0x18000f23e  lea     edx, [rbx+37h]
0x18000f241  mov     r9, rsi
0x18000f244  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f24b  call    WPP_SF_S
0x18000f250  lea     rax, [rsp+1D0h+var_1A0]
0x18000f255  mov     r9, rbx; AdapterAddresses
0x18000f258  xor     r8d, r8d; Reserved
0x18000f25b  mov     [rsp+1D0h+SizePointer], rax; SizePointer
0x18000f260  mov     edx, r14d; Flags
0x18000f263  xor     ecx, ecx; Family
0x18000f265  call    cs:__imp_GetAdaptersAddresses
0x18000f26b  cmp     eax, 6Fh ; 'o'
0x18000f26e  jnz     short loc_18000F28A
0x18000f270  mov     edx, [rsp+1D0h+var_1A0]; cb
0x18000f274  mov     rcx, rbx; pv
0x18000f277  call    cs:__imp_CoTaskMemRealloc
0x18000f27d  mov     rbx, rax
0x18000f280  test    rax, rax
0x18000f283  jnz     short loc_18000F250
0x18000f285  jmp     loc_18000F43E
0x18000f28a  mov     r14d, 80070000h
0x18000f290  test    eax, eax
0x18000f292  jle     short loc_18000F29C
0x18000f294  movzx   eax, ax
0x18000f297  or      eax, r14d
0x18000f29a  test    eax, eax
0x18000f29c  js      loc_18000F43E
0x18000f2a2  lea     r8, [rsp+1D0h+var_19C]; int *
0x18000f2a7  mov     rcx, rsi; AddressString
0x18000f2aa  lea     rdx, [rbp+0D0h+Src]; lpAddress
0x18000f2ae  call    ?IpStringToSockAddress@@YAJPEAGPEAUsockaddr_storage@@PEAH@Z; IpStringToSockAddress(ushort *,sockaddr_storage *,int *)
0x18000f2b3  test    eax, eax
0x18000f2b5  js      loc_18000F43E
0x18000f2bb  movsxd  r8, [rsp+1D0h+var_19C]
0x18000f2c0  lea     rdx, [rbp+0D0h+Src]; Src
0x18000f2c4  mov     esi, 1Ch
0x18000f2c9  lea     rcx, [rsp+1D0h+Row]; void *
0x18000f2ce  cmp     r8, rsi
0x18000f2d1  cmova   r8, rsi; Size
0x18000f2d5  call    memcpy_0
0x18000f2da  xor     edx, edx; SourceAddress
0x18000f2dc  lea     rcx, [rsp+1D0h+Row]; Row
0x18000f2e1  call    cs:__imp_ResolveIpNetEntry2
0x18000f2e7  mov     edi, eax
0x18000f2e9  test    eax, eax
0x18000f2eb  jle     short loc_18000F2F3
0x18000f2ed  movzx   edi, ax
0x18000f2f0  or      edi, r14d
0x18000f2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2fa  cmp     rcx, r13
0x18000f2fd  jz      short loc_18000F31D
0x18000f2ff  test    byte ptr [rcx+1Ch], 8
0x18000f303  jz      short loc_18000F31D
0x18000f305  mov     rcx, [rcx+10h]
0x18000f309  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f310  mov     edx, 38h ; '8'
0x18000f315  mov     r9d, edi
0x18000f318  call    WPP_SF_d
0x18000f31d  test    edi, edi
0x18000f31f  js      loc_18000F43E
0x18000f325  mov     r15, rbx
0x18000f328  test    rbx, rbx
0x18000f32b  jz      loc_18000F43E
0x18000f331  xor     eax, eax
0x18000f333  lea     rcx, [rbp+0D0h+Buf1.Address+2]; void *
0x18000f337  xor     edx, edx; Val
0x18000f339  mov     word ptr [rbp+0D0h+Buf1.Address], ax
0x18000f33d  lea     r8d, [rax+56h]; Size
0x18000f341  call    memset_0
0x18000f346  mov     r14, [r15+0D0h]
0x18000f34d  jmp     loc_18000F400
0x18000f352  movsxd  r8, dword ptr [r14+18h]
0x18000f356  lea     rcx, [rbp+0D0h+Buf1]; void *
0x18000f35a  mov     rdx, [r14+10h]; Src
0x18000f35e  cmp     r8, rsi
0x18000f361  cmova   r8, rsi; Size
0x18000f365  call    memcpy_0
0x18000f36a  xor     edx, edx; SourceAddress
0x18000f36c  lea     rcx, [rbp+0D0h+Buf1]; Row
0x18000f370  call    cs:__imp_ResolveIpNetEntry2
0x18000f376  mov     esi, eax
0x18000f378  test    eax, eax
0x18000f37a  jle     short loc_18000F385
0x18000f37c  movzx   esi, ax
0x18000f37f  or      esi, 80070000h
0x18000f385  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f38c  cmp     rdi, r13
0x18000f38f  jz      short loc_18000F3B6
0x18000f391  test    byte ptr [rdi+1Ch], 8
0x18000f395  jz      short loc_18000F3B6
0x18000f397  mov     rcx, [rdi+10h]
0x18000f39b  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f3a2  mov     edx, 39h ; '9'
0x18000f3a7  mov     r9d, esi
0x18000f3aa  call    WPP_SF_d
0x18000f3af  mov     rdi, cs:WPP_GLOBAL_Control
0x18000f3b6  test    esi, esi
0x18000f3b8  js      short loc_18000F3F7
0x18000f3ba  mov     eax, [rbp+0D0h+Row.PhysicalAddressLength]
0x18000f3bd  cmp     [rbp+0D0h+Buf1.PhysicalAddressLength], eax
0x18000f3c0  jnz     short loc_18000F3D7
0x18000f3c2  mov     r8d, eax; Size
0x18000f3c5  lea     rdx, [rsp+1D0h+Row.PhysicalAddress]; Buf2
0x18000f3ca  lea     rcx, [rbp+0D0h+Buf1.PhysicalAddress]; Buf1
0x18000f3ce  call    memcmp_0
0x18000f3d3  test    eax, eax
0x18000f3d5  jz      short loc_18000F418
0x18000f3d7  cmp     rdi, r13
0x18000f3da  jz      short loc_18000F3F7
0x18000f3dc  test    byte ptr [rdi+1Ch], 8
0x18000f3e0  jz      short loc_18000F3F7
0x18000f3e2  mov     rcx, [rdi+10h]
0x18000f3e6  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f3ed  mov     edx, 3Bh ; ';'
0x18000f3f2  call    WPP_SF_
0x18000f3f7  mov     r14, [r14+8]
0x18000f3fb  mov     esi, 1Ch
0x18000f400  test    r14, r14
0x18000f403  jnz     loc_18000F352
0x18000f409  mov     r15, [r15+8]
0x18000f40d  test    r15, r15
0x18000f410  jnz     loc_18000F331
0x18000f416  jmp     short loc_18000F43E
0x18000f418  cmp     rdi, r13
0x18000f41b  jz      short loc_18000F438
0x18000f41d  test    byte ptr [rdi+1Ch], 8
0x18000f421  jz      short loc_18000F438
0x18000f423  mov     rcx, [rdi+10h]
0x18000f427  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f42e  mov     edx, 3Ah ; ':'
0x18000f433  call    WPP_SF_
0x18000f438  mov     r12d, 1
0x18000f43e  mov     rcx, rbx; pv
0x18000f441  call    cs:__imp_CoTaskMemFree
0x18000f447  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f44e  cmp     rcx, r13
0x18000f451  jz      short loc_18000F46E
0x18000f453  test    byte ptr [rcx+1Ch], 20h
0x18000f457  jz      short loc_18000F46E
0x18000f459  mov     rcx, [rcx+10h]
0x18000f45d  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x18000f464  mov     edx, 3Ch ; '<'
0x18000f469  call    WPP_SF_
0x18000f46e  mov     eax, r12d
0x18000f471  mov     rcx, [rbp+0D0h+var_50]
0x18000f478  xor     rcx, rsp; StackCookie
0x18000f47b  call    __security_check_cookie
0x18000f480  add     rsp, 198h
0x18000f487  pop     r15
0x18000f489  pop     r14
0x18000f48b  pop     r13
0x18000f48d  pop     r12
0x18000f48f  pop     rdi
0x18000f490  pop     rsi
0x18000f491  pop     rbx
0x18000f492  pop     rbp
0x18000f493  retn
```
