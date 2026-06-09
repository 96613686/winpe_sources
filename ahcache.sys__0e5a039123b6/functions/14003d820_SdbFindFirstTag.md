# SdbFindFirstTag

- ea: `0x14003d820`
- end: `0x14003da44`
- name: `SdbFindFirstTag`
- size: `548`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `53`
- callee_count: `6`
- tags: ``

## callers

- `0x1400021a0`
- `0x140002a00`
- `0x1400030d0`
- `0x1400032fc`
- `0x140005f1c`
- `0x140006200`
- `0x1400062b0`
- `0x1400255d0`
- `0x140026550`
- `0x14002db98`
- `0x14002dc6c`
- `0x14002dd74`
- `0x14002e064`
- `0x14002e3b8`
- `0x14002ebc0`
- `0x14002ed10`
- `0x14002ef40`
- `0x14002f050`
- `0x14002f430`
- `0x14002f980`
- `0x14002fa60`
- `0x14002fb00`
- `0x14002fba0`
- `0x14002fc20`
- `0x14002fd64`
- `0x140030260`
- `0x140030304`
- `0x140038bd8`
- `0x140038fd4`
- `0x140039400`
- `0x140039898`
- `0x140039b18`
- `0x14003a2a8`
- `0x14003aa68`
- `0x14003af10`
- `0x14003b2f0`
- `0x14003b694`
- `0x14003bea8`
- `0x14003c010`
- `0x14003c364`
- `0x14003c710`
- `0x14003fe74`
- `0x140040730`
- `0x140040c08`
- `0x140040d5c`
- `0x1400412e8`
- `0x1400413ec`
- `0x140049ec0`
- `0x14004a1ac`
- `0x14004b4ac`

## callees

- `0x1400055d4`
- `0x14003d820`
- `0x14003e154`
- `0x14003e1f0`
- `0x14003e248`
- `0x14003e364`

## string_xrefs

- `0x14003d901`: `Error reading data`

## pseudocode

```c
__int64 __fastcall SdbFindFirstTag(__int64 a1, __int64 a2, __int16 a3)
{
  unsigned int v4; // ebp
  unsigned int NextTagId; // ebx
  unsigned int v7; // eax
  unsigned int v8; // r14d
  __int16 v9; // ax
  unsigned int v10; // ebx
  unsigned int v11; // edi
  __int16 v13; // [rsp+78h] [rbp+10h] BYREF

  v4 = a2;
  if ( (_DWORD)a2 )
  {
    if ( (SdbGetTagFromTagID(a1, a2) & 0xF000) != 0x7000 )
    {
      v8 = 0;
      goto LABEL_7;
    }
    NextTagId = SdbpGetNextTagId(a1, v4);
    if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
      && NextTagId > *(_DWORD *)(a1 + 20) )
    {
      AslLogCallPrintf(
        2,
        "SdbGetFirstChild",
        3141,
        "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; pdb->dwSize=0x%X)",
        v4,
        *(_DWORD *)(a1 + 20));
      v8 = 0;
      goto LABEL_7;
    }
    v7 = v4 + 6;
  }
  else
  {
    NextTagId = *(_DWORD *)(a1 + 20);
    v7 = 12;
  }
  v8 = 0;
  if ( v7 < NextTagId )
    v8 = v7;
LABEL_7:
  while ( v8 )
  {
    v13 = 0;
    if ( (unsigned int)SdbpReadMappedData(a1, v8, &v13, 2u) )
    {
      v9 = v13;
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetTagFromTagID", 3039, "Error reading data");
      v9 = 0;
    }
    if ( v9 == a3 )
      return v8;
    if ( !v4 )
    {
      v10 = *(_DWORD *)(a1 + 20);
      goto LABEL_13;
    }
    if ( (SdbGetTagFromTagID(a1, v4) & 0xF000) == 0x7000 )
    {
      v10 = SdbpGetNextTagId(a1, v4);
      if ( (unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline()
        && v10 > *(_DWORD *)(a1 + 20) )
      {
        AslLogCallPrintf(
          2,
          "SdbGetNextChild",
          3196,
          "SdbpGetNextTagId returned value larger than the SDB (for tiParent=0x%X; tiPrev=0x%X; pdb->dwSize=0x%X)",
          v4,
          v8,
          *(_DWORD *)(a1 + 20));
        v8 = 0;
      }
      else
      {
LABEL_13:
        v11 = SdbpGetNextTagId(a1, v8);
        if ( !(unsigned int)Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( v11 < v10 )
            goto LABEL_16;
LABEL_15:
          v11 = 0;
          goto LABEL_16;
        }
        if ( v11 >= v10 || v11 <= v8 )
          goto LABEL_15;
LABEL_16:
        v8 = v11;
      }
    }
    else
    {
      AslLogCallPrintf(1, "SdbGetNextChild", 3182, "Trying to operate on non-list, non-root tag");
      v8 = 0;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14003d820  mov     [rsp+arg_10], rbx
0x14003d825  mov     [rsp+arg_18], rbp
0x14003d82a  push    rsi
0x14003d82b  push    r12
0x14003d82d  push    r13
0x14003d82f  push    r14
0x14003d831  push    r15
0x14003d833  sub     rsp, 40h
0x14003d837  xor     r12d, r12d
0x14003d83a  movzx   r15d, r8w
0x14003d83e  mov     ebp, edx
0x14003d840  mov     rsi, rcx
0x14003d843  mov     ebx, 7000h
0x14003d848  mov     r13d, 0F000h
0x14003d84e  test    edx, edx
0x14003d850  jz      loc_14003D94B
0x14003d856  call    SdbGetTagFromTagID
0x14003d85b  and     ax, r13w
0x14003d85f  cmp     ax, bx
0x14003d862  jnz     loc_14003D9ED
0x14003d868  mov     edx, ebp
0x14003d86a  mov     rcx, rsi
0x14003d86d  call    SdbpGetNextTagId
0x14003d872  mov     ebx, eax
0x14003d874  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003d879  test    eax, eax
0x14003d87b  jnz     loc_14003D9F5
0x14003d881  lea     eax, [rbp+6]
0x14003d884  xor     r14d, r14d
0x14003d887  cmp     eax, ebx
0x14003d889  cmovb   r14d, eax
0x14003d88d  mov     ebx, 7000h
0x14003d892  mov     [rsp+68h+arg_0], rdi
0x14003d897  test    r14d, r14d
0x14003d89a  jz      loc_14003D946
0x14003d8a0  xor     eax, eax
0x14003d8a2  lea     r8, [rsp+68h+arg_8]
0x14003d8a7  mov     r9d, 2
0x14003d8ad  mov     [rsp+68h+arg_8], ax
0x14003d8b2  mov     edx, r14d
0x14003d8b5  mov     rcx, rsi
0x14003d8b8  call    SdbpReadMappedData
0x14003d8bd  test    eax, eax
0x14003d8bf  jz      short loc_14003D901
0x14003d8c1  movzx   eax, [rsp+68h+arg_8]
0x14003d8c6  cmp     ax, r15w
0x14003d8ca  jz      short loc_14003D923
0x14003d8cc  test    ebp, ebp
0x14003d8ce  jnz     loc_14003D9B4
0x14003d8d4  mov     ebx, [rsi+14h]
0x14003d8d7  mov     edx, r14d
0x14003d8da  mov     rcx, rsi
0x14003d8dd  call    SdbpGetNextTagId
0x14003d8e2  mov     edi, eax
0x14003d8e4  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003d8e9  test    eax, eax
0x14003d8eb  jnz     loc_14003DA2E
0x14003d8f1  cmp     edi, ebx
0x14003d8f3  jb      short loc_14003D8F7
0x14003d8f5  xor     edi, edi
0x14003d8f7  mov     r14d, edi
0x14003d8fa  mov     ebx, 7000h
0x14003d8ff  jmp     short loc_14003D897
0x14003d901  lea     r9, aErrorReadingDa; "Error reading data"
0x14003d908  mov     r8d, 0BDFh
0x14003d90e  lea     rdx, aSdbgettagfromt; "SdbGetTagFromTagID"
0x14003d915  mov     ecx, 1
0x14003d91a  call    AslLogCallPrintf
0x14003d91f  xor     eax, eax
0x14003d921  jmp     short loc_14003D8C6
0x14003d923  mov     eax, r14d
0x14003d926  mov     rdi, [rsp+68h+arg_0]
0x14003d92b  lea     r11, [rsp+68h+var_28]
0x14003d930  mov     rbx, [r11+40h]
0x14003d934  mov     rbp, [r11+48h]
0x14003d938  mov     rsp, r11
0x14003d93b  pop     r15
0x14003d93d  pop     r14
0x14003d93f  pop     r13
0x14003d941  pop     r12
0x14003d943  pop     rsi
0x14003d944  retn
0x14003d946  mov     eax, r12d
0x14003d949  jmp     short loc_14003D926
0x14003d94b  mov     ebx, [rcx+14h]
0x14003d94e  mov     eax, 0Ch
0x14003d953  jmp     loc_14003D884
0x14003d958  mov     edx, ebp
0x14003d95a  mov     rcx, rsi
0x14003d95d  call    SdbpGetNextTagId
0x14003d962  mov     ebx, eax
0x14003d964  call    Feature_SdbValidateRootTagsOnOpen__private_IsEnabledDeviceUsageNoInline
0x14003d969  test    eax, eax
0x14003d96b  jz      loc_14003D8D7
0x14003d971  mov     eax, [rsi+14h]
0x14003d974  cmp     ebx, eax
0x14003d976  jbe     loc_14003D8D7
0x14003d97c  mov     [rsp+68h+var_38], eax
0x14003d980  lea     r9, aSdbpgetnexttag; "SdbpGetNextTagId returned value larger "...
0x14003d987  mov     [rsp+68h+var_40], r14d
0x14003d98c  lea     rdx, aSdbgetnextchil; "SdbGetNextChild"
0x14003d993  mov     r8d, 0C7Ch
0x14003d999  mov     [rsp+68h+var_48], ebp
0x14003d99d  mov     ecx, 2
0x14003d9a2  call    AslLogCallPrintf
0x14003d9a7  xor     r14d, r14d
0x14003d9aa  mov     ebx, 7000h
0x14003d9af  jmp     loc_14003D897
0x14003d9b4  mov     edx, ebp
0x14003d9b6  mov     rcx, rsi
0x14003d9b9  call    SdbGetTagFromTagID
0x14003d9be  and     ax, r13w
0x14003d9c2  cmp     ax, bx
0x14003d9c5  jz      short loc_14003D958
0x14003d9c7  lea     r9, aTryingToOperat; "Trying to operate on non-list, non-root"...
0x14003d9ce  mov     r8d, 0C6Eh
0x14003d9d4  lea     rdx, aSdbgetnextchil; "SdbGetNextChild"
0x14003d9db  mov     ecx, 1
0x14003d9e0  call    AslLogCallPrintf
0x14003d9e5  xor     r14d, r14d
0x14003d9e8  jmp     loc_14003D897
0x14003d9ed  xor     r14d, r14d
0x14003d9f0  jmp     loc_14003D892
0x14003d9f5  mov     eax, [rsi+14h]
0x14003d9f8  cmp     ebx, eax
0x14003d9fa  jbe     loc_14003D881
0x14003da00  mov     [rsp+68h+var_40], eax
0x14003da04  lea     r9, aSdbpgetnexttag_1; "SdbpGetNextTagId returned value larger "...
0x14003da0b  mov     r8d, 0C45h
0x14003da11  mov     [rsp+68h+var_48], ebp
0x14003da15  lea     rdx, aSdbgetfirstchi; "SdbGetFirstChild"
0x14003da1c  mov     ecx, 2
0x14003da21  call    AslLogCallPrintf
0x14003da26  xor     r14d, r14d
0x14003da29  jmp     loc_14003D88D
0x14003da2e  cmp     edi, ebx
0x14003da30  jnb     loc_14003D8F5
0x14003da36  cmp     edi, r14d
0x14003da39  ja      loc_14003D8F7
0x14003da3f  jmp     loc_14003D8F5
```
