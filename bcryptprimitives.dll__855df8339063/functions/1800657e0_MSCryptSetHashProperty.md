# MSCryptSetHashProperty

- ea: `0x1800657e0`
- end: `0x180065a47`
- name: `MSCryptSetHashProperty`
- size: `615`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ecb0`
- `0x1800185c0`
- `0x180040e60`
- `0x180065680`
- `0x1800657e0`
- `0x18007f765`

## string_xrefs

- `0x180065a28`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\hash.c`

## pseudocode

```c
__int64 __fastcall MSCryptSetHashProperty(__int64 a1, __int64 a2, const void *a3, unsigned int a4, int a5)
{
  __int64 v6; // rbx
  __int64 v8; // r9
  unsigned int v9; // ebx
  __int64 v10; // rcx
  unsigned __int16 *v11; // rdx
  _DWORD *v12; // rdi
  __int64 v13; // r8
  int v14; // edx
  int v15; // eax
  int v16; // eax

  v6 = a4;
  if ( a5 )
  {
    v8 = 3837;
LABEL_3:
    v9 = -1073741811;
    v10 = 3221225485LL;
LABEL_45:
    DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\hash.c", v8);
    return v9;
  }
  v12 = (_DWORD *)validateMSCryptHash(a1, a2);
  if ( !v12 )
  {
    v9 = -1073741816;
    v8 = 3846;
    v10 = 3221225480LL;
    goto LABEL_45;
  }
  v14 = *v11 - 73;
  if ( !v14 )
  {
    v14 = *(unsigned __int16 *)(a2 + 2) - 86;
    if ( *(_WORD *)(a2 + 2) == 86 )
      v14 = *(unsigned __int16 *)(a2 + 4);
  }
  if ( v14 )
  {
    if ( !wcscmp_0((const wchar_t *)a2, L"FunctionNameString") )
    {
      if ( v12[2] == 131093 )
      {
        v15 = MSCryptCustomBufferUpdate((__int64)(v12 + 30), a3, v6);
        v9 = v15;
        if ( v15 < 0 )
        {
          v8 = 3895;
LABEL_21:
          v10 = (unsigned int)v15;
          goto LABEL_45;
        }
      }
      else
      {
        if ( v12[2] != 131094 )
        {
          v8 = 3918;
          goto LABEL_3;
        }
        v15 = MSCryptCustomBufferUpdate((__int64)(v12 + 30), a3, v6);
        v9 = v15;
        if ( v15 < 0 )
        {
          v8 = 3909;
          goto LABEL_21;
        }
      }
    }
    else
    {
      if ( wcscmp_0((const wchar_t *)a2, L"CustomizationString") )
      {
        v8 = 3996;
        goto LABEL_44;
      }
      v16 = v12[2];
      if ( v16 == 131093 )
      {
        v15 = MSCryptCustomBufferUpdate((__int64)(v12 + 50), a3, v6);
        v9 = v15;
        if ( v15 < 0 )
        {
          v8 = 3935;
          goto LABEL_21;
        }
      }
      else
      {
        if ( v16 != 131094 )
        {
          if ( v16 == 131095 )
          {
            v15 = MSCryptCustomBufferUpdate((__int64)(v12 + 112), a3, v6);
            v9 = v15;
            if ( v15 < 0 )
            {
              v8 = 3963;
              goto LABEL_21;
            }
          }
          else
          {
            if ( v16 != 131096 )
            {
              v8 = 3986;
              goto LABEL_3;
            }
            v15 = MSCryptCustomBufferUpdate((__int64)(v12 + 112), a3, v6);
            v9 = v15;
            if ( v15 < 0 )
            {
              v8 = 3977;
              goto LABEL_21;
            }
          }
          v12[132] = 0;
          return 0;
        }
        v15 = MSCryptCustomBufferUpdate((__int64)(v12 + 50), a3, v6);
        v9 = v15;
        if ( v15 < 0 )
        {
          v8 = 3949;
          goto LABEL_21;
        }
      }
    }
    v12[70] = 0;
    return 0;
  }
  if ( v12[2] != 131080 )
  {
    v8 = 3857;
LABEL_44:
    v10 = 3221225659LL;
    v9 = -1073741637;
    goto LABEL_45;
  }
  if ( (_DWORD)v6 != 12 )
  {
    v9 = -1073741306;
    v8 = 3868;
    v10 = 3221225990LL;
    goto LABEL_45;
  }
  if ( v12[29] )
  {
    v9 = -1073740758;
    v8 = 3878;
    v10 = 3221226538LL;
    goto LABEL_45;
  }
  SymCryptGcmInit(v12 + 684, v12 + 32, v13, v6);
  v12[29] = 1;
  return 0;
}

```

## disassembly

```asm
0x1800657e0  push    rbx
0x1800657e2  push    rbp
0x1800657e3  push    rsi
0x1800657e4  push    rdi
0x1800657e5  sub     rsp, 28h
0x1800657e9  cmp     [rsp+48h+arg_20], 0
0x1800657ee  mov     rbp, r8
0x1800657f1  mov     ebx, r9d
0x1800657f4  mov     rsi, rdx
0x1800657f7  jz      short loc_18006580E
0x1800657f9  mov     r9d, 0EFDh
0x1800657ff  mov     ebx, 0C000000Dh
0x180065804  mov     ecx, 0C000000Dh
0x180065809  jmp     loc_180065A28
0x18006580e  call    validateMSCryptHash
0x180065813  mov     rdi, rax
0x180065816  test    rax, rax
0x180065819  jnz     short loc_180065830
0x18006581b  mov     ebx, 0C0000008h
0x180065820  mov     r9d, 0F06h
0x180065826  mov     ecx, 0C0000008h
0x18006582b  jmp     loc_180065A28
0x180065830  movzx   edx, word ptr [rdx]
0x180065833  sub     edx, 49h ; 'I'
0x180065836  jnz     short loc_18006584C
0x180065838  movzx   edx, word ptr [rsi+2]
0x18006583c  sub     edx, 56h ; 'V'
0x18006583f  jnz     short loc_18006584C
0x180065841  movzx   edx, word ptr [rsi+4]
0x180065845  xor     eax, eax
0x180065847  movzx   ecx, ax
0x18006584a  sub     edx, ecx
0x18006584c  test    edx, edx
0x18006584e  jnz     short loc_1800658BC
0x180065850  cmp     dword ptr [rdi+8], 20008h
0x180065857  jz      short loc_180065864
0x180065859  mov     r9d, 0F11h
0x18006585f  jmp     loc_180065A1E
0x180065864  lea     eax, [rbx-0Ch]
0x180065867  test    eax, eax
0x180065869  jnz     short loc_1800658A7
0x18006586b  cmp     [rdi+74h], eax
0x18006586e  jz      short loc_180065885
0x180065870  mov     ebx, 0C000042Ah
0x180065875  mov     r9d, 0F26h
0x18006587b  mov     ecx, 0C000042Ah
0x180065880  jmp     loc_180065A28
0x180065885  mov     r9, rbx
0x180065888  lea     rdx, [rdi+80h]
0x18006588f  lea     rcx, [rdi+0AB0h]
0x180065896  call    SymCryptGcmInit
0x18006589b  mov     dword ptr [rdi+74h], 1
0x1800658a2  jmp     loc_18006592A
0x1800658a7  mov     ebx, 0C0000206h
0x1800658ac  mov     r9d, 0F1Ch
0x1800658b2  mov     ecx, 0C0000206h
0x1800658b7  jmp     loc_180065A28
0x1800658bc  lea     rdx, aFunctionnamest; "FunctionNameString"
0x1800658c3  mov     rcx, rsi; String1
0x1800658c6  call    wcscmp_0
0x1800658cb  test    eax, eax
0x1800658cd  jnz     short loc_18006593C
0x1800658cf  cmp     dword ptr [rdi+8], 20015h
0x1800658d6  jnz     short loc_1800658FA
0x1800658d8  lea     rcx, [rdi+78h]
0x1800658dc  mov     r8d, ebx
0x1800658df  mov     rdx, rbp
0x1800658e2  call    MSCryptCustomBufferUpdate
0x1800658e7  mov     ebx, eax
0x1800658e9  test    eax, eax
0x1800658eb  jns     short loc_180065920
0x1800658ed  mov     r9d, 0F37h
0x1800658f3  mov     ecx, eax
0x1800658f5  jmp     loc_180065A28
0x1800658fa  cmp     dword ptr [rdi+8], 20016h
0x180065901  jnz     short loc_180065931
0x180065903  lea     rcx, [rdi+78h]
0x180065907  mov     r8d, ebx
0x18006590a  mov     rdx, rbp
0x18006590d  call    MSCryptCustomBufferUpdate
0x180065912  mov     ebx, eax
0x180065914  test    eax, eax
0x180065916  jns     short loc_180065920
0x180065918  mov     r9d, 0F45h
0x18006591e  jmp     short loc_1800658F3
0x180065920  mov     dword ptr [rdi+118h], 0
0x18006592a  xor     ebx, ebx
0x18006592c  jmp     loc_180065A3B
0x180065931  mov     r9d, 0F4Eh
0x180065937  jmp     loc_1800657FF
0x18006593c  lea     rdx, aCustomizations; "CustomizationString"
0x180065943  mov     rcx, rsi; String1
0x180065946  call    wcscmp_0
0x18006594b  test    eax, eax
0x18006594d  jnz     loc_180065A18
0x180065953  mov     eax, [rdi+8]
0x180065956  cmp     eax, 20015h
0x18006595b  jnz     short loc_180065980
0x18006595d  lea     rcx, [rdi+0C8h]
0x180065964  mov     r8d, ebx
0x180065967  mov     rdx, rbp
0x18006596a  call    MSCryptCustomBufferUpdate
0x18006596f  mov     ebx, eax
0x180065971  test    eax, eax
0x180065973  jns     short loc_180065920
0x180065975  mov     r9d, 0F5Fh
0x18006597b  jmp     loc_1800658F3
0x180065980  cmp     eax, 20016h
0x180065985  jnz     short loc_1800659AA
0x180065987  lea     rcx, [rdi+0C8h]
0x18006598e  mov     r8d, ebx
0x180065991  mov     rdx, rbp
0x180065994  call    MSCryptCustomBufferUpdate
0x180065999  mov     ebx, eax
0x18006599b  test    eax, eax
0x18006599d  jns     short loc_180065920
0x18006599f  mov     r9d, 0F6Dh
0x1800659a5  jmp     loc_1800658F3
0x1800659aa  cmp     eax, 20017h
0x1800659af  jnz     short loc_1800659D4
0x1800659b1  lea     rcx, [rdi+1C0h]
0x1800659b8  mov     r8d, ebx
0x1800659bb  mov     rdx, rbp
0x1800659be  call    MSCryptCustomBufferUpdate
0x1800659c3  mov     ebx, eax
0x1800659c5  test    eax, eax
0x1800659c7  jns     short loc_1800659FE
0x1800659c9  mov     r9d, 0F7Bh
0x1800659cf  jmp     loc_1800658F3
0x1800659d4  cmp     eax, 20018h
0x1800659d9  jnz     short loc_180065A0D
0x1800659db  lea     rcx, [rdi+1C0h]
0x1800659e2  mov     r8d, ebx
0x1800659e5  mov     rdx, rbp
0x1800659e8  call    MSCryptCustomBufferUpdate
0x1800659ed  mov     ebx, eax
0x1800659ef  test    eax, eax
0x1800659f1  jns     short loc_1800659FE
0x1800659f3  mov     r9d, 0F89h
0x1800659f9  jmp     loc_1800658F3
0x1800659fe  mov     dword ptr [rdi+210h], 0
0x180065a08  jmp     loc_18006592A
0x180065a0d  mov     r9d, 0F92h
0x180065a13  jmp     loc_1800657FF
0x180065a18  mov     r9d, 0F9Ch
0x180065a1e  mov     ecx, 0C00000BBh
0x180065a23  mov     ebx, 0C00000BBh
0x180065a28  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180065a2f  lea     rdx, aStatus; "Status"
0x180065a36  call    DebugTraceError
0x180065a3b  mov     eax, ebx
0x180065a3d  add     rsp, 28h
0x180065a41  pop     rdi
0x180065a42  pop     rsi
0x180065a43  pop     rbp
0x180065a44  pop     rbx
0x180065a45  retn
```
