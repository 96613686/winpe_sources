# BinXmlWriter::AddToken(BinXmlToken const &)

- ea: `0x18002e29c`
- end: `0x18002e471`
- name: `?AddToken@BinXmlWriter@@QEAAXAEBUBinXmlToken@@@Z`
- size: `469`
- prototype: `void __fastcall(BinXmlWriter *__hidden this, const struct BinXmlToken *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x18002ee5c`
- `0x18002fd5c`

## callees

- `0x180023548`
- `0x180024388`
- `0x18002e29c`
- `0x18002e4e4`
- `0x18002e5f0`
- `0x18002e628`
- `0x18002e660`
- `0x18002e89c`
- `0x18002e8d0`
- `0x18002e944`
- `0x18002eab4`
- `0x18002eafc`
- `0x18002f50c`
- `0x18002f5c0`
- `0x18002f7ec`
- `0x180038fb4`

## pseudocode

```c
void __fastcall BinXmlWriter::AddToken(BinXmlWriter *this, const struct BinXmlToken *a2)
{
  int v2; // r8d
  int v3; // r8d
  int v4; // r8d
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  bool v8; // dl
  __int64 v9; // rax
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  __int64 v16; // rax
  __int64 v17; // [rsp+20h] [rbp-40h] BYREF
  __int64 v18; // [rsp+28h] [rbp-38h]
  __int128 pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h]
  int v21; // [rsp+48h] [rbp-18h]
  int v22; // [rsp+4Ch] [rbp-14h]
  int v23; // [rsp+50h] [rbp-10h]

  v2 = *((_DWORD *)a2 + 4);
  if ( v2 > 7 )
  {
    v10 = v2 - 8;
    if ( v10 )
    {
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( !v14 )
              goto LABEL_30;
            v15 = v14 - 1;
            if ( v15 )
            {
              if ( v15 != 1 )
                goto LABEL_30;
              BinXmlWriter::WriteDependentSubstitution(this, a2, *((unsigned __int16 *)a2 + 1), *(unsigned __int16 *)a2);
            }
            else
            {
              BinXmlWriter::WriteSubstitution(this, 13, *((unsigned __int16 *)a2 + 1), *(unsigned __int16 *)a2);
            }
          }
          else
          {
            v16 = -1;
            do
              ++v16;
            while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v16) );
            v17 = *(_QWORD *)a2;
            v18 = v16;
            BinXmlWriter::PIData(this, &v17);
          }
        }
        else
        {
          BinXmlWriter::PITarget(this, *(const struct BinXmlString **)a2);
        }
      }
      else
      {
        BinXmlWriter::EntityRef(this, *(const struct BinXmlString **)a2);
      }
    }
    else
    {
      BinXmlWriter::CharRef(this, *(_WORD *)a2);
    }
    return;
  }
  if ( v2 == 7 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(*(_QWORD *)a2 + 2 * v9) );
    v17 = *(_QWORD *)a2;
    v18 = v9;
    BinXmlWriter::CDATA(this, &v17);
    return;
  }
  if ( !v2 )
  {
    BinXmlWriter::EndOfFile(this);
    return;
  }
  v3 = v2 - 1;
  if ( !v3 )
  {
    BinXmlWriter::OpenStartElementTag(this, *(const struct BinXmlString **)a2);
    return;
  }
  v4 = v3 - 1;
  if ( !v4 )
  {
    v8 = 0;
    goto LABEL_15;
  }
  v5 = v4 - 1;
  if ( !v5 )
  {
    v8 = 1;
LABEL_15:
    BinXmlWriter::CloseStartElementTag(this, v8);
    return;
  }
  v6 = v5 - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        BinXmlWriter::Attribute(this, *(const struct BinXmlString **)a2);
        return;
      }
LABEL_30:
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 13);
      }
      v20 = 0;
      v21 = 13;
      v22 = -1;
      pExceptionObject = 0;
      v23 = 1008;
      throw (EvtException *)&pExceptionObject;
    }
    BinXmlWriter::Value(this, a2);
  }
  else
  {
    BinXmlWriter::EndElementTag(this);
  }
}

```

## disassembly

```asm
0x18002e29c  mov     [rsp-8+arg_0], rbx
0x18002e2a1  push    rbp
0x18002e2a2  mov     rbp, rsp
0x18002e2a5  sub     rsp, 60h
0x18002e2a9  mov     r8d, [rdx+10h]
0x18002e2ad  xor     ebx, ebx
0x18002e2af  cmp     r8d, 7
0x18002e2b3  jg      loc_18002E357
0x18002e2b9  jz      short loc_18002E330
0x18002e2bb  test    r8d, r8d
0x18002e2be  jz      short loc_18002E326
0x18002e2c0  sub     r8d, 1
0x18002e2c4  jz      short loc_18002E319
0x18002e2c6  sub     r8d, 1
0x18002e2ca  jz      short loc_18002E30D
0x18002e2cc  sub     r8d, 1
0x18002e2d0  jz      short loc_18002E309
0x18002e2d2  sub     r8d, 1
0x18002e2d6  jz      short loc_18002E2FF
0x18002e2d8  sub     r8d, 1
0x18002e2dc  jz      short loc_18002E2F5
0x18002e2de  cmp     r8d, 1
0x18002e2e2  jnz     loc_18002E3BC
0x18002e2e8  mov     rdx, [rdx]; struct BinXmlString *
0x18002e2eb  call    ?Attribute@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::Attribute(BinXmlString const &)
0x18002e2f0  jmp     loc_18002E466
0x18002e2f5  call    ?Value@BinXmlWriter@@QEAAXAEBUBinXmlVariant@@@Z; BinXmlWriter::Value(BinXmlVariant const &)
0x18002e2fa  jmp     loc_18002E466
0x18002e2ff  call    ?EndElementTag@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndElementTag(void)
0x18002e304  jmp     loc_18002E466
0x18002e309  mov     dl, 1
0x18002e30b  jmp     short loc_18002E30F
0x18002e30d  xor     edx, edx; bool
0x18002e30f  call    ?CloseStartElementTag@BinXmlWriter@@QEAAX_N@Z; BinXmlWriter::CloseStartElementTag(bool)
0x18002e314  jmp     loc_18002E466
0x18002e319  mov     rdx, [rdx]; struct BinXmlString *
0x18002e31c  call    ?OpenStartElementTag@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::OpenStartElementTag(BinXmlString const &)
0x18002e321  jmp     loc_18002E466
0x18002e326  call    ?EndOfFile@BinXmlWriter@@QEAAXXZ; BinXmlWriter::EndOfFile(void)
0x18002e32b  jmp     loc_18002E466
0x18002e330  mov     r8, [rdx]
0x18002e333  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e337  inc     rax
0x18002e33a  cmp     [r8+rax*2], bx
0x18002e33f  jnz     short loc_18002E337
0x18002e341  lea     rdx, [rbp+var_40]
0x18002e345  mov     [rbp+var_40], r8
0x18002e349  mov     [rbp+var_38], rax
0x18002e34d  call    ?CDATA@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::CDATA(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002e352  jmp     loc_18002E466
0x18002e357  sub     r8d, 8
0x18002e35b  jz      loc_18002E45E
0x18002e361  sub     r8d, 1
0x18002e365  jz      loc_18002E454
0x18002e36b  sub     r8d, 1
0x18002e36f  jz      loc_18002E44A
0x18002e375  sub     r8d, 1
0x18002e379  jz      loc_18002E426
0x18002e37f  sub     r8d, 1
0x18002e383  jz      short loc_18002E3BC
0x18002e385  sub     r8d, 1
0x18002e389  jz      short loc_18002E3A4
0x18002e38b  cmp     r8d, 1
0x18002e38f  jnz     short loc_18002E3BC
0x18002e391  movzx   r8d, word ptr [rdx+2]
0x18002e396  movzx   r9d, word ptr [rdx]
0x18002e39a  call    ?WriteDependentSubstitution@BinXmlWriter@@AEAAXW4BinXmlTokType@@W4BinXmlVarType@@G@Z; BinXmlWriter::WriteDependentSubstitution(BinXmlTokType,BinXmlVarType,ushort)
0x18002e39f  jmp     loc_18002E466
0x18002e3a4  movzx   r8d, word ptr [rdx+2]
0x18002e3a9  movzx   r9d, word ptr [rdx]
0x18002e3ad  mov     edx, 0Dh
0x18002e3b2  call    ?WriteSubstitution@BinXmlWriter@@AEAAXW4BinXmlTokType@@W4BinXmlVarType@@G@Z; BinXmlWriter::WriteSubstitution(BinXmlTokType,BinXmlVarType,ushort)
0x18002e3b7  jmp     loc_18002E466
0x18002e3bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e3c3  lea     rax, WPP_GLOBAL_Control
0x18002e3ca  cmp     rcx, rax
0x18002e3cd  jz      short loc_18002E3F4
0x18002e3cf  test    byte ptr [rcx+1Ch], 2
0x18002e3d3  jz      short loc_18002E3F4
0x18002e3d5  cmp     byte ptr [rcx+19h], 2
0x18002e3d9  jb      short loc_18002E3F4
0x18002e3db  mov     rcx, [rcx+10h]
0x18002e3df  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002e3e6  mov     edx, 16h
0x18002e3eb  lea     r9d, [rdx-9]
0x18002e3ef  call    WPP_SF_D
0x18002e3f4  xorps   xmm0, xmm0
0x18002e3f7  mov     [rbp+var_20], rbx
0x18002e3fb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002e402  mov     [rbp+var_18], 0Dh
0x18002e409  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18002e40d  mov     [rbp+var_14], 0FFFFFFFFh
0x18002e414  movdqu  [rbp+pExceptionObject], xmm0
0x18002e419  mov     [rbp+var_10], 3F0h
0x18002e420  call    _CxxThrowException_0
0x18002e426  mov     r8, [rdx]
0x18002e429  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e42d  inc     rax
0x18002e430  cmp     [r8+rax*2], bx
0x18002e435  jnz     short loc_18002E42D
0x18002e437  lea     rdx, [rbp+var_40]
0x18002e43b  mov     [rbp+var_40], r8
0x18002e43f  mov     [rbp+var_38], rax
0x18002e443  call    ?PIData@BinXmlWriter@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::PIData(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002e448  jmp     short loc_18002E466
0x18002e44a  mov     rdx, [rdx]; struct BinXmlString *
0x18002e44d  call    ?PITarget@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::PITarget(BinXmlString const &)
0x18002e452  jmp     short loc_18002E466
0x18002e454  mov     rdx, [rdx]; struct BinXmlString *
0x18002e457  call    ?EntityRef@BinXmlWriter@@QEAAXAEBVBinXmlString@@@Z; BinXmlWriter::EntityRef(BinXmlString const &)
0x18002e45c  jmp     short loc_18002E466
0x18002e45e  movzx   edx, word ptr [rdx]; wchar_t
0x18002e461  call    ?CharRef@BinXmlWriter@@QEAAX_W@Z; BinXmlWriter::CharRef(wchar_t)
0x18002e466  mov     rbx, [rsp+60h+arg_0]
0x18002e46b  add     rsp, 60h
0x18002e46f  pop     rbp
0x18002e470  retn
```
