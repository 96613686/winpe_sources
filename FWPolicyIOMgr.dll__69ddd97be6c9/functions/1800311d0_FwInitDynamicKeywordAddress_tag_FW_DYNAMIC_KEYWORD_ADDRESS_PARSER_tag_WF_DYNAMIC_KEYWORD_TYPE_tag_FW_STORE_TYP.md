# FwInitDynamicKeywordAddress(_tag_FW_DYNAMIC_KEYWORD_ADDRESS_PARSER *,_tag_WF_DYNAMIC_KEYWORD_TYPE,_tag_FW_STORE_TYPE,ushort const *,ushort const *,_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL *)

- ea: `0x1800311d0`
- end: `0x1800312df`
- name: `?FwInitDynamicKeywordAddress@@YAJPEAU_tag_FW_DYNAMIC_KEYWORD_ADDRESS_PARSER@@W4_tag_WF_DYNAMIC_KEYWORD_TYPE@@W4_tag_FW_STORE_TYPE@@PEBG3PEAU_tag_FW_DYNAMIC_KEYWORD_ADDRESS_INTERNAL@@@Z`
- size: `271`
- prototype: `__int64 __fastcall(struct _tag_FW_DYNAMIC_KEYWORD_ADDRESS_PARSER *, int, unsigned int, const OLECHAR *, __int64, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019108`

## callees

- `0x1800042c4`
- `0x18001ffd4`
- `0x18002f520`
- `0x1800311d0`
- `0x1800312f0`
- `0x180031878`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031209`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180031209`

## pseudocode

```c
__int64 __fastcall FwInitDynamicKeywordAddress(
        struct _tag_FW_DYNAMIC_KEYWORD_ADDRESS_PARSER *a1,
        int a2,
        unsigned int a3,
        const OLECHAR *a4,
        __int64 a5,
        char *a6)
{
  HRESULT v10; // eax
  unsigned int v11; // ebx
  LPCOLESTR v12; // rcx
  __int64 v13; // rdx

  memset_0(a6, 0, 0x80u);
  v10 = CLSIDFromString(a4, (LPCLSID)(a6 + 12));
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        (unsigned int)WPP_4fd836f4550d30cdc57214e7ec8fd182_Traceguids,
        (_DWORD)a4,
        a5);
    v10 = FwDecodeDynamicKeywordAddress(a1);
    v11 = v10;
    if ( v10 >= 0 )
    {
      if ( !a2 )
        *((_DWORD *)a6 + 10) |= 1u;
      *((_DWORD *)a6 + 30) = FwGetDynamicKeywordOriginFromStoreType(a3);
    }
    else
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v13 = 22;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 20;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_4fd836f4550d30cdc57214e7ec8fd182_Traceguids, (unsigned int)v10);
    }
  }
  return v11;
}

```

## disassembly

```asm
0x1800311d0  push    rbx
0x1800311d2  push    rbp
0x1800311d3  push    rsi
0x1800311d4  push    rdi
0x1800311d5  push    r12
0x1800311d7  push    r14
0x1800311d9  push    r15
0x1800311db  sub     rsp, 30h
0x1800311df  mov     rsi, [rsp+68h+arg_28]
0x1800311e7  mov     r15d, r8d
0x1800311ea  mov     ebp, edx
0x1800311ec  mov     r12, rcx
0x1800311ef  mov     rcx, rsi; void *
0x1800311f2  xor     edx, edx; Val
0x1800311f4  mov     r8d, 80h; Size
0x1800311fa  mov     r14, r9
0x1800311fd  call    memset_0
0x180031202  lea     rdx, [rsi+0Ch]; pclsid
0x180031206  mov     rcx, r14; lpsz
0x180031209  call    cs:__imp_CLSIDFromString
0x18003120f  mov     ebx, eax
0x180031211  test    eax, eax
0x180031213  jns     short loc_180031250
0x180031215  mov     rcx, cs:WPP_GLOBAL_Control
0x18003121c  lea     rdi, WPP_GLOBAL_Control
0x180031223  cmp     rcx, rdi
0x180031226  jz      loc_1800312CE
0x18003122c  test    byte ptr [rcx+1Ch], 1
0x180031230  jz      loc_1800312CE
0x180031236  mov     edx, 14h
0x18003123b  mov     rcx, [rcx+10h]
0x18003123f  lea     r8, WPP_4fd836f4550d30cdc57214e7ec8fd182_Traceguids
0x180031246  mov     r9d, eax
0x180031249  call    WPP_SF_d
0x18003124e  jmp     short loc_1800312CE
0x180031250  mov     rcx, cs:WPP_GLOBAL_Control
0x180031257  lea     rdi, WPP_GLOBAL_Control
0x18003125e  mov     rbx, [rsp+68h+arg_20]
0x180031266  cmp     rcx, rdi
0x180031269  jz      short loc_18003128E
0x18003126b  test    byte ptr [rcx+1Ch], 4
0x18003126f  jz      short loc_18003128E
0x180031271  mov     rcx, [rcx+10h]
0x180031275  lea     r8, WPP_4fd836f4550d30cdc57214e7ec8fd182_Traceguids
0x18003127c  mov     edx, 15h
0x180031281  mov     [rsp+68h+var_48], rbx
0x180031286  mov     r9, r14
0x180031289  call    WPP_SF_SS
0x18003128e  mov     r8, rsi
0x180031291  mov     rdx, rbx
0x180031294  mov     rcx, r12; struct _tag_FW_DYNAMIC_KEYWORD_ADDRESS_PARSER *
0x180031297  call    FwDecodeDynamicKeywordAddress
0x18003129c  mov     ebx, eax
0x18003129e  test    eax, eax
0x1800312a0  jns     short loc_1800312BB
0x1800312a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312a9  cmp     rcx, rdi
0x1800312ac  jz      short loc_1800312CE
0x1800312ae  test    byte ptr [rcx+1Ch], 1
0x1800312b2  jz      short loc_1800312CE
0x1800312b4  mov     edx, 16h
0x1800312b9  jmp     short loc_18003123B
0x1800312bb  test    ebp, ebp
0x1800312bd  jnz     short loc_1800312C3
0x1800312bf  or      dword ptr [rsi+28h], 1
0x1800312c3  mov     ecx, r15d
0x1800312c6  call    FwGetDynamicKeywordOriginFromStoreType
0x1800312cb  mov     [rsi+78h], eax
0x1800312ce  mov     eax, ebx
0x1800312d0  add     rsp, 30h
0x1800312d4  pop     r15
0x1800312d6  pop     r14
0x1800312d8  pop     r12
0x1800312da  pop     rdi
0x1800312db  pop     rsi
0x1800312dc  pop     rbp
0x1800312dd  pop     rbx
0x1800312de  retn
```
