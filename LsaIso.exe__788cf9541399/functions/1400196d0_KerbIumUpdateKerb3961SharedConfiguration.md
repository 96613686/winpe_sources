# KerbIumUpdateKerb3961SharedConfiguration

- ea: `0x1400196d0`
- end: `0x14001978b`
- name: `KerbIumUpdateKerb3961SharedConfiguration`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x14001193c`
- `0x140011964`
- `0x1400196d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140019724`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140019724`
- `KerbClientShared!KerbClient3961UpdateSharedConfiguration` at `0x140019750`
- `KerbClientShared!KerbClient3961UpdateSharedConfiguration` at `0x140019750`

## pseudocode

```c
__int64 __fastcall KerbIumUpdateKerb3961SharedConfiguration(__int64 a1, unsigned int a2, unsigned __int8 *a3)
{
  unsigned __int64 v4; // rsi
  PVOID *v6; // rcx
  unsigned int v8; // ebx

  v4 = a2;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( qword_140052C40 == a1 )
  {
    if ( (_DWORD)v4 )
    {
      if ( a3 )
      {
        v8 = 0;
        KerbClient3961UpdateSharedConfiguration(a3, v4);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      else
      {
        v8 = -1073741584;
      }
    }
    else
    {
      v8 = -1073741585;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 )
      WPP_SF_d(v6[2], 132, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids, v8);
    return v8;
  }
  else
  {
    Sleep(5u);
    return 3221225506LL;
  }
}

```

## disassembly

```asm
0x1400196d0  push    rbx
0x1400196d2  push    rbp
0x1400196d3  push    rsi
0x1400196d4  push    rdi
0x1400196d5  sub     rsp, 28h
0x1400196d9  mov     rdi, r8
0x1400196dc  mov     esi, edx
0x1400196de  mov     rbx, rcx
0x1400196e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196e8  lea     rbp, WPP_GLOBAL_Control
0x1400196ef  cmp     rcx, rbp
0x1400196f2  jz      short loc_140019716
0x1400196f4  test    byte ptr [rcx+1Ch], 4
0x1400196f8  jz      short loc_140019716
0x1400196fa  mov     rcx, [rcx+10h]
0x1400196fe  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140019705  mov     edx, 83h
0x14001970a  call    WPP_SF_
0x14001970f  mov     rcx, cs:WPP_GLOBAL_Control
0x140019716  cmp     cs:qword_140052C40, rbx
0x14001971d  jz      short loc_140019731
0x14001971f  mov     ecx, 5; dwMilliseconds
0x140019724  call    cs:__imp_Sleep
0x14001972a  mov     eax, 0C0000022h
0x14001972f  jmp     short loc_140019782
0x140019731  test    esi, esi
0x140019733  jnz     short loc_14001973C
0x140019735  mov     ebx, 0C00000EFh
0x14001973a  jmp     short loc_14001975D
0x14001973c  test    rdi, rdi
0x14001973f  jnz     short loc_140019748
0x140019741  mov     ebx, 0C00000F0h
0x140019746  jmp     short loc_14001975D
0x140019748  xor     ebx, ebx
0x14001974a  mov     rdx, rsi
0x14001974d  mov     rcx, rdi
0x140019750  call    cs:__imp_?KerbClient3961UpdateSharedConfiguration@@YAJPEAE_K@Z; KerbClient3961UpdateSharedConfiguration(uchar *,unsigned __int64)
0x140019756  mov     rcx, cs:WPP_GLOBAL_Control
0x14001975d  cmp     rcx, rbp
0x140019760  jz      short loc_140019780
0x140019762  test    byte ptr [rcx+1Ch], 1
0x140019766  jz      short loc_140019780
0x140019768  mov     rcx, [rcx+10h]
0x14001976c  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140019773  mov     edx, 84h
0x140019778  mov     r9d, ebx
0x14001977b  call    WPP_SF_d
0x140019780  mov     eax, ebx
0x140019782  add     rsp, 28h
0x140019786  pop     rdi
0x140019787  pop     rsi
0x140019788  pop     rbp
0x140019789  pop     rbx
0x14001978a  retn
```
