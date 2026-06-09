# ZtTrustedServersConfiguredGlobal

- ea: `0x180010b6c`
- end: `0x180010c11`
- name: `ZtTrustedServersConfiguredGlobal`
- size: `165`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180004e18`

## callees

- `0x180010b6c`
- `0x180015008`

## pseudocode

```c
__int64 __fastcall ZtTrustedServersConfiguredGlobal(int a1)
{
  __int64 v1; // rdi
  unsigned int v2; // ebx
  char v3; // al

  v1 = a1;
  v2 = 0;
  v3 = BYTE1(xmmword_18001F260);
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
  {
    WPP_SF_d(1035, 0xEu, (ULONGLONG)WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids, a1);
    v3 = BYTE1(xmmword_18001F260);
  }
  if ( (unsigned int)v1 <= 1 )
  {
    if ( g_pDnsZtServers[v1] )
      LOBYTE(v2) = g_cDnsZtServers[v1] != 0;
  }
  else
  {
    if ( (v3 & 8) == 0 )
      return v2;
    WPP_SF_d(1035, 0xFu, (ULONGLONG)WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids, v1);
    v3 = BYTE1(xmmword_18001F260);
  }
  if ( (v3 & 8) != 0 )
    WPP_SF_d(1035, 0x10u, (ULONGLONG)WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids, v2);
  return v2;
}

```

## disassembly

```asm
0x180010b6c  mov     [rsp+arg_0], rbx
0x180010b71  push    rdi
0x180010b72  sub     rsp, 20h
0x180010b76  movsxd  rdi, ecx
0x180010b79  xor     ebx, ebx
0x180010b7b  mov     al, byte ptr cs:xmmword_18001F260+1
0x180010b81  test    al, 8
0x180010b83  jz      short loc_180010BA2
0x180010b85  lea     edx, [rbx+0Eh]
0x180010b88  mov     ecx, 40Bh
0x180010b8d  mov     r9d, edi
0x180010b90  lea     r8, WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids
0x180010b97  call    WPP_SF_d
0x180010b9c  mov     al, byte ptr cs:xmmword_18001F260+1
0x180010ba2  cmp     edi, 1
0x180010ba5  jbe     short loc_180010BCC
0x180010ba7  test    al, 8
0x180010ba9  jz      short loc_180010C04
0x180010bab  mov     edx, 0Fh
0x180010bb0  lea     r8, WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids
0x180010bb7  mov     ecx, 40Bh
0x180010bbc  mov     r9d, edi
0x180010bbf  call    WPP_SF_d
0x180010bc4  mov     al, byte ptr cs:xmmword_18001F260+1
0x180010bca  jmp     short loc_180010BE7
0x180010bcc  lea     rcx, cs:180000000h
0x180010bd3  cmp     rva g_pDnsZtServers[rcx+rdi*8], rbx
0x180010bdb  jz      short loc_180010BE7
0x180010bdd  cmp     rva g_cDnsZtServers[rcx+rdi*4], ebx
0x180010be4  setnbe  bl
0x180010be7  test    al, 8
0x180010be9  jz      short loc_180010C04
0x180010beb  mov     edx, 10h
0x180010bf0  lea     r8, WPP_cbd6223456ee357e6d251c3ed41b29e6_Traceguids
0x180010bf7  mov     ecx, 40Bh
0x180010bfc  mov     r9d, ebx
0x180010bff  call    WPP_SF_d
0x180010c04  mov     eax, ebx
0x180010c06  mov     rbx, [rsp+28h+arg_0]
0x180010c0b  add     rsp, 20h
0x180010c0f  pop     rdi
0x180010c10  retn
```
