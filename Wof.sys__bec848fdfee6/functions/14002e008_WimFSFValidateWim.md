# WimFSFValidateWim

- ea: `0x14002e008`
- end: `0x14002e23e`
- name: `WimFSFValidateWim`
- size: `566`
- prototype: `NTSTATUS __fastcall(struct _FLT_INSTANCE *, struct _FILE_OBJECT *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002da7c`

## callees

- `0x14000d3b8`
- `0x14000fb60`
- `0x140010320`
- `0x1400105e8`
- `0x140011560`
- `0x14002e008`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14002e079`
- `ntoskrnl!RtlCompareMemory` at `0x14002e079`
- `FLTMGR!FltQueryInformationFile` at `0x14002e059`
- `FLTMGR!FltQueryInformationFile` at `0x14002e059`

## pseudocode

```c
NTSTATUS __fastcall WimFSFValidateWim(struct _FLT_INSTANCE *a1, struct _FILE_OBJECT *a2, __int64 a3, _QWORD *a4)
{
  int v6; // ebx
  NTSTATUS result; // eax
  int v8; // edx
  int v9; // r8d
  __int64 v10; // r9
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int128 v15; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+40h] [rbp-38h]
  __int64 Source2; // [rsp+48h] [rbp-30h] BYREF

  Source2 = 0x4D4957534DLL;
  v15 = 0;
  v6 = 0;
  v16 = 0;
  result = FltQueryInformationFile(a1, a2, &v15, 0x18u, FileStandardInformation, 0);
  if ( result >= 0 )
  {
    if ( RtlCompareMemory((const void *)a3, &Source2, 8u) != 8 )
    {
      v6 = -1073700187;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids, a3);
      return v6;
    }
    v10 = *(unsigned int *)(a3 + 8);
    if ( (_DWORD)v10 == 208 )
    {
      v10 = *(unsigned int *)(a3 + 12);
      if ( (_DWORD)v10 == 68864 )
      {
        if ( (*(_BYTE *)(a3 + 16) & 0x38) != 0 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids);
          return -1073741637;
        }
        else
        {
          if ( !a4 )
            goto LABEL_23;
          v13 = *(_QWORD *)(a3 + 24) - *a4;
          if ( !v13 )
            v13 = *(_QWORD *)(a3 + 32) - a4[1];
          if ( v13 )
          {
            v6 = -1073700187;
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF__guid__guid_(WPP_GLOBAL_Control->AttachedDevice, v8, v9, a3 + 24, (__int64)a4);
          }
          else
          {
LABEL_23:
            v14 = *(_QWORD *)(a3 + 56);
            if ( v14 > *((__int64 *)&v15 + 1)
              || v14 + (*(_QWORD *)(a3 + 48) & 0xFFFFFFFFFFFFFFLL) > *((__int64 *)&v15 + 1) )
            {
              v6 = -1073700186;
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids);
            }
          }
        }
        return v6;
      }
      v6 = -1073700187;
      v11 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return v6;
      v12 = 18;
    }
    else
    {
      v6 = -1073700187;
      v11 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        return v6;
      v12 = 17;
    }
    WPP_SF_d(v11->AttachedDevice, v12, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids, v10);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14002e008  mov     r11, rsp
0x14002e00b  push    rbx
0x14002e00c  push    rsi
0x14002e00d  push    rdi
0x14002e00e  sub     rsp, 60h
0x14002e012  mov     rax, cs:__security_cookie
0x14002e019  xor     rax, rsp
0x14002e01c  mov     [rsp+78h+var_28], rax
0x14002e021  mov     rax, 4D4957534Dh
0x14002e02b  xorps   xmm0, xmm0
0x14002e02e  mov     [r11-30h], rax
0x14002e032  mov     rsi, r9
0x14002e035  xor     eax, eax
0x14002e037  mov     rdi, r8
0x14002e03a  movups  [rsp+78h+var_48], xmm0
0x14002e03f  xor     ebx, ebx
0x14002e041  mov     [r11-38h], rax
0x14002e045  mov     [r11-50h], rbx
0x14002e049  lea     r8, [r11-48h]; FileInformation
0x14002e04d  lea     r9d, [rax+18h]; Length
0x14002e051  mov     [rsp+78h+FileInformationClass], 5; FileInformationClass
0x14002e059  call    cs:__imp_FltQueryInformationFile
0x14002e060  nop     dword ptr [rax+rax+00h]
0x14002e065  test    eax, eax
0x14002e067  js      loc_14002E228
0x14002e06d  lea     r8d, [rbx+8]; Length
0x14002e071  mov     rcx, rdi; Source1
0x14002e074  lea     rdx, [rsp+78h+Source2]; Source2
0x14002e079  call    cs:__imp_RtlCompareMemory
0x14002e080  nop     dword ptr [rax+rax+00h]
0x14002e085  cmp     rax, 8
0x14002e089  jz      short loc_14002E0C9
0x14002e08b  mov     ebx, 0C000A2A5h
0x14002e090  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e097  mov     eax, [rcx+2Ch]
0x14002e09a  test    al, 8
0x14002e09c  jz      loc_14002E226
0x14002e0a2  cmp     byte ptr [rcx+29h], 2
0x14002e0a6  jb      loc_14002E226
0x14002e0ac  mov     rcx, [rcx+18h]
0x14002e0b0  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e0b7  mov     edx, 10h
0x14002e0bc  mov     r9, rdi
0x14002e0bf  call    WPP_SF_s
0x14002e0c4  jmp     loc_14002E226
0x14002e0c9  mov     r9d, [rdi+8]
0x14002e0cd  cmp     r9d, 0D0h
0x14002e0d4  jz      short loc_14002E0FE
0x14002e0d6  mov     ebx, 0C000A2A5h
0x14002e0db  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e0e2  mov     eax, [rcx+2Ch]
0x14002e0e5  test    al, 8
0x14002e0e7  jz      loc_14002E226
0x14002e0ed  cmp     byte ptr [rcx+29h], 2
0x14002e0f1  jb      loc_14002E226
0x14002e0f7  mov     edx, 11h
0x14002e0fc  jmp     short loc_14002E131
0x14002e0fe  mov     r9d, [rdi+0Ch]
0x14002e102  cmp     r9d, 10D00h
0x14002e109  jz      short loc_14002E146
0x14002e10b  mov     ebx, 0C000A2A5h
0x14002e110  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e117  mov     eax, [rcx+2Ch]
0x14002e11a  test    al, 8
0x14002e11c  jz      loc_14002E226
0x14002e122  cmp     byte ptr [rcx+29h], 2
0x14002e126  jb      loc_14002E226
0x14002e12c  mov     edx, 12h
0x14002e131  mov     rcx, [rcx+18h]
0x14002e135  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e13c  call    WPP_SF_d
0x14002e141  jmp     loc_14002E226
0x14002e146  test    byte ptr [rdi+10h], 38h
0x14002e14a  jnz     loc_14002E1F8
0x14002e150  test    rsi, rsi
0x14002e153  jz      short loc_14002E1A2
0x14002e155  lea     r9, [rdi+18h]
0x14002e159  mov     rcx, [r9]
0x14002e15c  sub     rcx, [rsi]
0x14002e15f  jnz     short loc_14002E169
0x14002e161  mov     rcx, [r9+8]
0x14002e165  sub     rcx, [rsi+8]
0x14002e169  test    rcx, rcx
0x14002e16c  jz      short loc_14002E1A2
0x14002e16e  mov     ebx, 0C000A2A5h
0x14002e173  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e17a  mov     eax, [rcx+2Ch]
0x14002e17d  test    al, 8
0x14002e17f  jz      loc_14002E226
0x14002e185  cmp     byte ptr [rcx+29h], 2
0x14002e189  jb      loc_14002E226
0x14002e18f  mov     rcx, [rcx+18h]
0x14002e193  mov     qword ptr [rsp+78h+FileInformationClass], rsi
0x14002e198  call    WPP_SF__guid__guid_
0x14002e19d  jmp     loc_14002E226
0x14002e1a2  mov     rcx, [rdi+38h]
0x14002e1a6  cmp     rcx, qword ptr [rsp+78h+var_48+8]
0x14002e1ab  jg      short loc_14002E1C8
0x14002e1ad  mov     rax, [rdi+30h]
0x14002e1b1  mov     rdx, 0FFFFFFFFFFFFFFh
0x14002e1bb  and     rax, rdx
0x14002e1be  add     rax, rcx
0x14002e1c1  cmp     rax, qword ptr [rsp+78h+var_48+8]
0x14002e1c6  jle     short loc_14002E226
0x14002e1c8  mov     ebx, 0C000A2A6h
0x14002e1cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1d4  mov     eax, [rcx+2Ch]
0x14002e1d7  test    al, 8
0x14002e1d9  jz      short loc_14002E226
0x14002e1db  cmp     byte ptr [rcx+29h], 2
0x14002e1df  jb      short loc_14002E226
0x14002e1e1  mov     rcx, [rcx+18h]
0x14002e1e5  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e1ec  mov     edx, 15h
0x14002e1f1  call    WPP_SF_
0x14002e1f6  jmp     short loc_14002E226
0x14002e1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002e1ff  mov     eax, [rcx+2Ch]
0x14002e202  test    al, 8
0x14002e204  jz      short loc_14002E221
0x14002e206  cmp     byte ptr [rcx+29h], 2
0x14002e20a  jb      short loc_14002E221
0x14002e20c  mov     rcx, [rcx+18h]
0x14002e210  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x14002e217  mov     edx, 13h
0x14002e21c  call    WPP_SF_
0x14002e221  mov     ebx, 0C00000BBh
0x14002e226  mov     eax, ebx
0x14002e228  mov     rcx, [rsp+78h+var_28]
0x14002e22d  xor     rcx, rsp; StackCookie
0x14002e230  call    __security_check_cookie
0x14002e235  add     rsp, 60h
0x14002e239  pop     rdi
0x14002e23a  pop     rsi
0x14002e23b  pop     rbx
0x14002e23c  retn
```
