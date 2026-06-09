# MSCryptDestroySecret

- ea: `0x180010bb0`
- end: `0x180010cb4`
- name: `MSCryptDestroySecret`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006bd38`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x180010bb0`

## string_xrefs

- `0x180010c08`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`
- `0x180010c5d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`

## pseudocode

```c
__int64 __fastcall MSCryptDestroySecret(_DWORD *a1, int a2, int a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rax
  _BYTE *v5; // rdx

  if ( a1 )
  {
    if ( *a1 >= 0x280u && a1[1] == 1297302851 )
    {
      v3 = 0;
      v4 = (unsigned int)a1[3] + 640LL;
      v5 = a1;
      do
      {
        *v5++ = 0;
        --v4;
      }
      while ( v4 );
      MSCryptFree(a1);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          640,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c",
          87);
      v3 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c", 317);
    }
  }
  else
  {
    v3 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c",
        54);
  }
  return v3;
}

```

## disassembly

```asm
0x180010bb0  mov     [rsp+arg_0], rbx
0x180010bb5  push    rdi
0x180010bb6  sub     rsp, 40h
0x180010bba  test    rcx, rcx
0x180010bbd  jz      short loc_180010C3B
0x180010bbf  mov     edx, 280h
0x180010bc4  cmp     [rcx], edx
0x180010bc6  jb      short loc_180010BFA
0x180010bc8  cmp     dword ptr [rcx+4], 4D534543h
0x180010bcf  jnz     short loc_180010BFA
0x180010bd1  mov     eax, [rcx+0Ch]
0x180010bd4  xor     ebx, ebx
0x180010bd6  add     rax, rdx
0x180010bd9  mov     rdx, rcx
0x180010bdc  mov     [rdx], bl
0x180010bde  inc     rdx
0x180010be1  sub     rax, 1
0x180010be5  jnz     short loc_180010BDC
0x180010be7  call    MSCryptFree
0x180010bec  mov     eax, ebx
0x180010bee  mov     rbx, [rsp+48h+arg_0]
0x180010bf3  add     rsp, 40h
0x180010bf7  pop     rdi
0x180010bf8  retn
0x180010bfa  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c01  lea     rax, WPP_GLOBAL_Control
0x180010c08  lea     rdi, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010c0f  cmp     rcx, rax
0x180010c12  jz      short loc_180010C1A
0x180010c14  test    byte ptr [rcx+1Ch], 1
0x180010c18  jnz     short loc_180010C8A
0x180010c1a  mov     r9d, 13Dh
0x180010c20  lea     rdx, aStatus; "Status"
0x180010c27  mov     r8, rdi
0x180010c2a  mov     ecx, 0C000000Dh
0x180010c2f  mov     ebx, 0C000000Dh
0x180010c34  call    DebugTraceError
0x180010c39  jmp     short loc_180010BEC
0x180010c3b  mov     ebx, 0C000000Dh
0x180010c40  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c47  lea     rax, WPP_GLOBAL_Control
0x180010c4e  cmp     rcx, rax
0x180010c51  jz      short loc_180010BEC
0x180010c53  test    byte ptr [rcx+1Ch], 1
0x180010c57  jz      short loc_180010BEC
0x180010c59  mov     rcx, [rcx+10h]
0x180010c5d  lea     rdi, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010c64  mov     [rsp+48h+var_18], 136h
0x180010c6c  lea     r9, aStatus; "Status"
0x180010c73  mov     [rsp+48h+var_20], rdi
0x180010c78  mov     [rsp+48h+var_28], 0C000000Dh
0x180010c80  call    WPP_SF_sDsd
0x180010c85  jmp     loc_180010BEC
0x180010c8a  mov     rcx, [rcx+10h]
0x180010c8e  lea     r9, aStatus; "Status"
0x180010c95  mov     [rsp+48h+var_18], 57h ; 'W'
0x180010c9d  mov     [rsp+48h+var_20], rdi
0x180010ca2  mov     [rsp+48h+var_28], 0C000000Dh
0x180010caa  call    WPP_SF_sDsd
0x180010caf  jmp     loc_180010C1A
```
