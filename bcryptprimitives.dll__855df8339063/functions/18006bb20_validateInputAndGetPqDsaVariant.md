# validateInputAndGetPqDsaVariant

- ea: `0x18006bb20`
- end: `0x18006bcbc`
- name: `validateInputAndGetPqDsaVariant`
- size: `412`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, int, int *, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006b3e0`
- `0x18006b6b0`

## callees

- `0x18000ecb0`
- `0x18006bad0`
- `0x18006bb20`

## string_xrefs

- `0x18006bb58`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall validateInputAndGetPqDsaVariant(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        int a5,
        int *a6,
        _DWORD *a7)
{
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rcx
  int v12; // edi
  __int64 v13; // r10
  __int64 v14; // r9
  int v15; // edx
  int v16; // eax
  __int64 PreHashInfo; // rax

  if ( (~*(_DWORD *)(*(_QWORD *)(a1 + 16) + 20LL) & a5) == 0 )
  {
    if ( (a5 & 0x20) != 0 )
    {
      if ( (a5 & 0x40) != 0 )
      {
        v8 = 403;
        goto LABEL_3;
      }
      v9 = 0;
      if ( a4 )
      {
        if ( !*(_QWORD *)a4 && *(_DWORD *)(a4 + 8) )
        {
          v8 = 420;
          goto LABEL_3;
        }
        if ( *(_DWORD *)(a4 + 8) > 0xFFu )
        {
          v8 = 427;
          goto LABEL_3;
        }
        v11 = *(unsigned __int16 **)(a4 + 16);
        if ( v11 )
        {
          if ( !a2 || !a3 )
          {
            v8 = 470;
            goto LABEL_3;
          }
          v12 = 2;
          if ( *(_DWORD *)(a1 + 8) == 196620 )
          {
            PreHashInfo = getPreHashInfo();
            if ( !PreHashInfo )
            {
              v8 = 481;
              goto LABEL_3;
            }
            *a7 = *(_DWORD *)(PreHashInfo + 8);
          }
          else
          {
            if ( *(_DWORD *)(a1 + 8) != 196621 )
            {
              v9 = -1073741816;
              v8 = 506;
              v10 = 3221225480LL;
              goto LABEL_4;
            }
            v13 = *(_QWORD *)(a1 + 24);
            v14 = *(_QWORD *)(v13 + 32) - (_QWORD)v11;
            do
            {
              v15 = *(unsigned __int16 *)((char *)v11 + v14);
              v16 = *v11 - v15;
              if ( v16 )
                break;
              ++v11;
            }
            while ( v15 );
            if ( v16 )
            {
              v8 = 492;
              goto LABEL_3;
            }
            if ( a3 != *(_DWORD *)(v13 + 40) )
            {
              v8 = 498;
              goto LABEL_3;
            }
          }
LABEL_30:
          *a6 = v12;
          return v9;
        }
        goto LABEL_39;
      }
    }
    else
    {
      v9 = 0;
      if ( !a4 )
      {
        if ( (a5 & 0x40) != 0 )
        {
          if ( !a2 || (v12 = 1, a3 != 64) )
          {
            v8 = 442;
            goto LABEL_3;
          }
          goto LABEL_30;
        }
LABEL_39:
        v12 = 0;
        if ( !a2 && a3 )
        {
          v8 = 456;
          goto LABEL_3;
        }
        goto LABEL_30;
      }
    }
    v8 = 411;
    goto LABEL_3;
  }
  v8 = 396;
LABEL_3:
  v9 = -1073741811;
  v10 = 3221225485LL;
LABEL_4:
  DebugTraceError(v10, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v8);
  return v9;
}

```

## disassembly

```asm
0x18006bb20  mov     [rsp+arg_0], rbx
0x18006bb25  push    rdi
0x18006bb26  sub     rsp, 20h
0x18006bb2a  mov     rax, [rcx+10h]
0x18006bb2e  mov     r11, rcx
0x18006bb31  mov     r10d, [rax+14h]
0x18006bb35  mov     eax, [rsp+28h+arg_20]
0x18006bb39  not     r10d
0x18006bb3c  test    eax, r10d
0x18006bb3f  jz      short loc_18006BB69
0x18006bb41  mov     r9d, 18Ch
0x18006bb47  mov     ebx, 0C000000Dh
0x18006bb4c  mov     ecx, 0C000000Dh
0x18006bb51  lea     rdx, aStatus_0; "status"
0x18006bb58  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006bb5f  call    DebugTraceError
0x18006bb64  jmp     loc_18006BC5B
0x18006bb69  test    al, 20h
0x18006bb6b  jz      loc_18006BC74
0x18006bb71  test    al, 40h
0x18006bb73  jz      short loc_18006BB7D
0x18006bb75  mov     r9d, 193h
0x18006bb7b  jmp     short loc_18006BB47
0x18006bb7d  xor     ebx, ebx
0x18006bb7f  test    r9, r9
0x18006bb82  jz      loc_18006BC7B
0x18006bb88  cmp     [r9], rbx
0x18006bb8b  jnz     short loc_18006BB9B
0x18006bb8d  cmp     [r9+8], ebx
0x18006bb91  jz      short loc_18006BB9B
0x18006bb93  mov     r9d, 1A4h
0x18006bb99  jmp     short loc_18006BB47
0x18006bb9b  cmp     dword ptr [r9+8], 0FFh
0x18006bba3  jbe     short loc_18006BBAD
0x18006bba5  mov     r9d, 1ABh
0x18006bbab  jmp     short loc_18006BB47
0x18006bbad  mov     rcx, [r9+10h]
0x18006bbb1  test    rcx, rcx
0x18006bbb4  jz      loc_18006BCA5
0x18006bbba  test    rdx, rdx
0x18006bbbd  jz      loc_18006BC69
0x18006bbc3  test    r8d, r8d
0x18006bbc6  jz      loc_18006BC69
0x18006bbcc  mov     edx, [r11+8]
0x18006bbd0  mov     edi, 2
0x18006bbd5  sub     edx, 3000Ch
0x18006bbdb  jz      short loc_18006BC35
0x18006bbdd  cmp     edx, 1
0x18006bbe0  jz      short loc_18006BBF7
0x18006bbe2  mov     ebx, 0C0000008h
0x18006bbe7  mov     r9d, 1FAh
0x18006bbed  mov     ecx, 0C0000008h
0x18006bbf2  jmp     loc_18006BB51
0x18006bbf7  mov     r10, [r11+18h]
0x18006bbfb  mov     r9, [r10+20h]
0x18006bbff  sub     r9, rcx
0x18006bc02  movzx   eax, word ptr [rcx]
0x18006bc05  movzx   edx, word ptr [rcx+r9]
0x18006bc0a  sub     eax, edx
0x18006bc0c  jnz     short loc_18006BC15
0x18006bc0e  add     rcx, rdi
0x18006bc11  test    edx, edx
0x18006bc13  jnz     short loc_18006BC02
0x18006bc15  test    eax, eax
0x18006bc17  jz      short loc_18006BC24
0x18006bc19  mov     r9d, 1ECh
0x18006bc1f  jmp     loc_18006BB47
0x18006bc24  cmp     r8d, [r10+28h]
0x18006bc28  jz      short loc_18006BC54
0x18006bc2a  mov     r9d, 1F2h
0x18006bc30  jmp     loc_18006BB47
0x18006bc35  call    getPreHashInfo
0x18006bc3a  test    rax, rax
0x18006bc3d  jnz     short loc_18006BC4A
0x18006bc3f  mov     r9d, 1E1h
0x18006bc45  jmp     loc_18006BB47
0x18006bc4a  mov     ecx, [rax+8]
0x18006bc4d  mov     rax, [rsp+28h+arg_30]
0x18006bc52  mov     [rax], ecx
0x18006bc54  mov     rcx, [rsp+28h+arg_28]
0x18006bc59  mov     [rcx], edi
0x18006bc5b  mov     eax, ebx
0x18006bc5d  mov     rbx, [rsp+28h+arg_0]
0x18006bc62  add     rsp, 20h
0x18006bc66  pop     rdi
0x18006bc67  retn
0x18006bc69  mov     r9d, 1D6h
0x18006bc6f  jmp     loc_18006BB47
0x18006bc74  xor     ebx, ebx
0x18006bc76  test    r9, r9
0x18006bc79  jz      short loc_18006BC86
0x18006bc7b  mov     r9d, 19Bh
0x18006bc81  jmp     loc_18006BB47
0x18006bc86  test    al, 40h
0x18006bc88  jz      short loc_18006BCA5
0x18006bc8a  test    rdx, rdx
0x18006bc8d  jz      short loc_18006BC9A
0x18006bc8f  mov     edi, 1
0x18006bc94  cmp     r8d, 40h ; '@'
0x18006bc98  jz      short loc_18006BC54
0x18006bc9a  mov     r9d, 1BAh
0x18006bca0  jmp     loc_18006BB47
0x18006bca5  mov     edi, ebx
0x18006bca7  test    rdx, rdx
0x18006bcaa  jnz     short loc_18006BC54
0x18006bcac  test    r8d, r8d
0x18006bcaf  jz      short loc_18006BC54
0x18006bcb1  mov     r9d, 1C8h
0x18006bcb7  jmp     loc_18006BB47
```
