# AccessStartedEventIOCTLCallback(_REDIRECTION_CONTEXT *)

- ea: `0x180012c10`
- end: `0x180012d77`
- name: `?AccessStartedEventIOCTLCallback@@YAXPEAU_REDIRECTION_CONTEXT@@@Z`
- size: `359`
- prototype: `void __fastcall(struct _REDIRECTION_CONTEXT *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18000605c`
- `0x180007bc0`
- `0x180012878`
- `0x180012c10`
- `0x180016d20`
- `0x18001904c`
- `0x18001991c`
- `0x18001be10`
- `0x18002e3a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012c3a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012d31`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012cf0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180012cf0`

## string_xrefs

- `0x180012d0e`: `SCREDIR: AccessStartedEventIOCTLCallback - Status = %lx\n`

## pseudocode

```c
void __fastcall AccessStartedEventIOCTLCallback(struct _REDIRECTION_CONTEXT *a1)
{
  int v2; // edi
  __int64 v3; // rcx
  int v4; // r8d
  int v5; // r9d
  int v6; // r9d
  unsigned int v7; // edx
  __int64 v8; // rcx
  int v9; // r9d
  char v10[256]; // [rsp+30h] [rbp-118h] BYREF

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  WppTraceIndent(v3, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sld(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v4, v5, 224, *((_DWORD *)a1 + 50));
  }
  v6 = *((_DWORD *)a1 + 50);
  if ( v6 )
  {
    if ( v6 != -1073741536 || *((_BYTE *)a1 + 40) )
      StringCbPrintfA(v10, 0x100u, "SCREDIR: AccessStartedEventIOCTLCallback - Status = %lx\n", v6);
    else
      v2 = 1;
  }
  else
  {
    v7 = *((_DWORD *)a1 + 52);
    *((_DWORD *)a1 + 118) = v7;
    if ( !(unsigned int)I_DecodeLongReturn((char *)a1 + 216, v7) )
    {
      WppTraceIndent(v8, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
          v9,
          *((_DWORD *)a1 + 18));
      }
      SetEvent(*((HANDLE *)a1 + 17));
    }
  }
  *((_DWORD *)a1 + 36) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  RedirectionContextRelease(a1);
  if ( v2 )
  {
    if ( !*((_BYTE *)a1 + 40) )
      _SetStartedEventToCorrectState(a1);
  }
}

```

## disassembly

```asm
0x180012c10  mov     [rsp+arg_8], rbx
0x180012c15  mov     [rsp+arg_10], rdi
0x180012c1a  push    r14
0x180012c1c  sub     rsp, 140h
0x180012c23  mov     rax, cs:__security_cookie
0x180012c2a  xor     rax, rsp
0x180012c2d  mov     [rsp+148h+var_18], rax
0x180012c35  mov     rbx, rcx
0x180012c38  xor     edi, edi
0x180012c3a  call    cs:__imp_EnterCriticalSection
0x180012c40  lea     edx, [rdi+2]
0x180012c43  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012c48  mov     rcx, cs:WPP_GLOBAL_Control
0x180012c4f  lea     r14, WPP_GLOBAL_Control
0x180012c56  cmp     rcx, r14
0x180012c59  jz      short loc_180012C85
0x180012c5b  test    byte ptr [rcx+1Ch], 8
0x180012c5f  jz      short loc_180012C85
0x180012c61  cmp     byte ptr [rcx+19h], 4
0x180012c65  jb      short loc_180012C85
0x180012c67  mov     eax, [rbx+0C8h]
0x180012c6d  lea     edx, [rdi+0Ah]
0x180012c70  mov     rcx, [rcx+10h]
0x180012c74  mov     [rsp+148h+var_120], eax
0x180012c78  mov     [rsp+148h+var_128], 900E0h
0x180012c80  call    WPP_SF_sld
0x180012c85  mov     r9d, [rbx+0C8h]
0x180012c8c  test    r9d, r9d
0x180012c8f  jnz     short loc_180012CF8
0x180012c91  mov     edx, [rbx+0D0h]; unsigned int
0x180012c97  lea     rcx, [rbx+0D8h]; unsigned __int8 *
0x180012c9e  mov     [rbx+1D8h], edx
0x180012ca4  call    ?I_DecodeLongReturn@@YAJPEAEK@Z; I_DecodeLongReturn(uchar *,ulong)
0x180012ca9  test    eax, eax
0x180012cab  jnz     short loc_180012D24
0x180012cad  lea     edx, [rax+2]
0x180012cb0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180012cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012cbc  cmp     rcx, r14
0x180012cbf  jz      short loc_180012CE9
0x180012cc1  test    byte ptr [rcx+1Ch], 1
0x180012cc5  jz      short loc_180012CE9
0x180012cc7  cmp     byte ptr [rcx+19h], 4
0x180012ccb  jb      short loc_180012CE9
0x180012ccd  mov     eax, [rbx+48h]
0x180012cd0  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x180012cd7  mov     rcx, [rcx+10h]
0x180012cdb  mov     edx, 0Bh
0x180012ce0  mov     [rsp+148h+var_128], eax
0x180012ce4  call    WPP_SF_sd
0x180012ce9  mov     rcx, [rbx+88h]; hEvent
0x180012cf0  call    cs:__imp_SetEvent
0x180012cf6  jmp     short loc_180012D24
0x180012cf8  cmp     r9d, 0C0000120h
0x180012cff  jnz     short loc_180012D0E
0x180012d01  cmp     [rbx+28h], dil
0x180012d05  jnz     short loc_180012D0E
0x180012d07  mov     edi, 1
0x180012d0c  jmp     short loc_180012D24
0x180012d0e  lea     r8, aScredirAccesss; "SCREDIR: AccessStartedEventIOCTLCallbac"...
0x180012d15  mov     edx, 100h; unsigned __int64
0x180012d1a  lea     rcx, [rsp+148h+var_118]; char *
0x180012d1f  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x180012d24  mov     rcx, rbx; lpCriticalSection
0x180012d27  mov     dword ptr [rbx+90h], 0
0x180012d31  call    cs:__imp_LeaveCriticalSection
0x180012d37  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x180012d3a  call    ?RedirectionContextRelease@@YAKPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextRelease(_REDIRECTION_CONTEXT *)
0x180012d3f  test    edi, edi
0x180012d41  jz      short loc_180012D51
0x180012d43  cmp     byte ptr [rbx+28h], 0
0x180012d47  jnz     short loc_180012D51
0x180012d49  mov     rcx, rbx; struct _REDIRECTION_CONTEXT *
0x180012d4c  call    ?_SetStartedEventToCorrectState@@YAHPEAU_REDIRECTION_CONTEXT@@@Z; _SetStartedEventToCorrectState(_REDIRECTION_CONTEXT *)
0x180012d51  mov     rcx, [rsp+148h+var_18]
0x180012d59  xor     rcx, rsp; StackCookie
0x180012d5c  call    __security_check_cookie
0x180012d61  lea     r11, [rsp+148h+var_8]
0x180012d69  mov     rbx, [r11+18h]
0x180012d6d  mov     rdi, [r11+20h]
0x180012d71  mov     rsp, r11
0x180012d74  pop     r14
0x180012d76  retn
```
