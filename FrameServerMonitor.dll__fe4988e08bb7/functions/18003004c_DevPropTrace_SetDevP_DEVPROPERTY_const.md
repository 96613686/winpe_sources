# DevPropTrace::SetDevP(_DEVPROPERTY const &)

- ea: `0x18003004c`
- end: `0x18003024c`
- name: `?SetDevP@DevPropTrace@@QEAAXAEBU_DEVPROPERTY@@@Z`
- size: `512`
- prototype: `void __fastcall(DevPropTrace *__hidden this, const struct _DEVPROPERTY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001e86c`

## callees

- `0x1800019f0`
- `0x180011438`
- `0x18002fa3c`
- `0x18002fa98`
- `0x18002fd04`
- `0x18003004c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ltoa_s` at `0x1800300f2`
- `api-ms-win-crt-private-l1-1-0!_o__ltoa_s` at `0x1800300f2`

## string_xrefs

- `0x180030130`: `_UserSidString`
- `0x18003011e`: `_SymbolicName`
- `0x18003010c`: `_RegistryBlob`

## pseudocode

```c
void __fastcall DevPropTrace::SetDevP(DevPropTrace *this, const struct _DEVPROPERTY *a2)
{
  __int64 v4; // rax
  int *p_pid; // rsi
  char *v6; // rdi
  ULONG BufferSize; // ebp
  PVOID v8; // rbx
  DEVPROPTYPE Type; // edi
  int v10; // esi
  GuidTrace *v11; // rax
  const char *v12; // rax
  const struct std::nothrow_t *v13; // rdx
  PVOID v14; // rbx
  GuidTrace *v15; // rax
  const char *String; // rax
  PVOID v17; // rbx
  GuidTrace *v18; // rax
  const char *v19; // rax
  char v20[32]; // [rsp+40h] [rbp-68h] BYREF
  char Buffer[8]; // [rsp+60h] [rbp-48h] BYREF
  int v22; // [rsp+68h] [rbp-40h]
  char v23; // [rsp+6Ch] [rbp-3Ch]

  *(_QWORD *)Buffer = 0;
  v22 = 0;
  v23 = 0;
  v4 = *(_QWORD *)&a2->CompKey.Key.fmtid.Data1 - 0x4BD03393B3E34238LL;
  if ( *(_QWORD *)&a2->CompKey.Key.fmtid.Data1 == 0x4BD03393B3E34238LL )
    v4 = *(_QWORD *)a2->CompKey.Key.fmtid.Data4 + 0xE43CD6123C60353LL;
  p_pid = (int *)&a2->CompKey.Key.pid;
  if ( v4 )
  {
    v6 = 0;
  }
  else
  {
    switch ( *p_pid )
    {
      case 3:
        v6 = "_Data";
        break;
      case 4:
        v6 = "_Categories";
        break;
      case 5:
        v6 = "_Attributes";
        break;
      case 6:
        v6 = "_Properties";
        break;
      case 7:
        v6 = "_UserSidString";
        break;
      case 8:
        v6 = "_SourceId";
        break;
      case 9:
        v6 = "_SymbolicName";
        break;
      case 10:
        v6 = "_InternalAlias";
        break;
      case 11:
        v6 = "_RegistryBlob";
        break;
      default:
        if ( _ltoa_s(*p_pid, Buffer, 0xDu, 10) )
          v6 = "_ERROR";
        else
          v6 = Buffer;
        break;
    }
  }
  BufferSize = a2->BufferSize;
  if ( v6 )
  {
    if ( BufferSize && a2->Type == 18 )
    {
      v14 = a2->Buffer;
      v15 = GuidTrace::GuidTrace((GuidTrace *)v20, &a2->CompKey.Key.fmtid);
      String = GuidTrace::GetString(v15);
      FSString::SetFormatString(this, "%s%s,value=%ws", String, v6, v14);
    }
    else
    {
      v17 = a2->Buffer;
      v18 = GuidTrace::GuidTrace((GuidTrace *)v20, &a2->CompKey.Key.fmtid);
      v19 = GuidTrace::GetString(v18);
      FSString::SetFormatString(this, "%s%s,value=0x%p,size=%u", v19, v6, v17, BufferSize);
    }
  }
  else
  {
    v8 = a2->Buffer;
    Type = a2->Type;
    v10 = *p_pid;
    v11 = GuidTrace::GuidTrace((GuidTrace *)v20, &a2->CompKey.Key.fmtid);
    v12 = GuidTrace::GetString(v11);
    FSString::SetFormatString(this, "%s,%d,type=%d,value=0x%p,size=%u", v12, v10, Type, v8, BufferSize);
  }
  FSString::~FSString((FSString *)v20, v13);
}

```

## disassembly

```asm
0x18003004c  mov     [rsp+arg_10], rbx
0x180030051  push    rbp
0x180030052  push    rsi
0x180030053  push    rdi
0x180030054  push    r14
0x180030056  push    r15
0x180030058  sub     rsp, 80h
0x18003005f  mov     rax, cs:__security_cookie
0x180030066  xor     rax, rsp
0x180030069  mov     [rsp+0A8h+var_38], rax
0x18003006e  xor     eax, eax
0x180030070  mov     r14, rdx
0x180030073  mov     qword ptr [rsp+0A8h+Buffer], rax
0x180030078  mov     r15, rcx
0x18003007b  mov     [rsp+0A8h+var_40], eax
0x18003007f  mov     [rsp+0A8h+var_3C], al
0x180030083  mov     rax, [rdx]
0x180030086  sub     rax, cs:qword_1800557C8
0x18003008d  jnz     short loc_18003009A
0x18003008f  mov     rax, [rdx+8]
0x180030093  sub     rax, cs:qword_1800557D0
0x18003009a  lea     rsi, [rdx+10h]
0x18003009e  test    rax, rax
0x1800300a1  jz      short loc_1800300AA
0x1800300a3  xor     edi, edi
0x1800300a5  jmp     loc_18003015B
0x1800300aa  mov     eax, [rsi]
0x1800300ac  sub     eax, 3
0x1800300af  jz      loc_180030154
0x1800300b5  sub     eax, 1
0x1800300b8  jz      loc_18003014B
0x1800300be  sub     eax, 1
0x1800300c1  jz      short loc_180030142
0x1800300c3  sub     eax, 1
0x1800300c6  jz      short loc_180030139
0x1800300c8  sub     eax, 1
0x1800300cb  jz      short loc_180030130
0x1800300cd  sub     eax, 1
0x1800300d0  jz      short loc_180030127
0x1800300d2  sub     eax, 1
0x1800300d5  jz      short loc_18003011E
0x1800300d7  sub     eax, 1
0x1800300da  jz      short loc_180030115
0x1800300dc  cmp     eax, 1
0x1800300df  jz      short loc_18003010C
0x1800300e1  mov     ecx, [rsi]; Value
0x1800300e3  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x1800300e8  mov     r9d, 0Ah; Radix
0x1800300ee  lea     r8d, [r9+3]; BufferCount
0x1800300f2  call    cs:__imp__ltoa_s
0x1800300f8  test    eax, eax
0x1800300fa  jz      short loc_180030105
0x1800300fc  lea     rdi, aError; "_ERROR"
0x180030103  jmp     short loc_18003015B
0x180030105  lea     rdi, [rsp+0A8h+Buffer]
0x18003010a  jmp     short loc_18003015B
0x18003010c  lea     rdi, aRegistryblob; "_RegistryBlob"
0x180030113  jmp     short loc_18003015B
0x180030115  lea     rdi, aInternalalias; "_InternalAlias"
0x18003011c  jmp     short loc_18003015B
0x18003011e  lea     rdi, aSymbolicname; "_SymbolicName"
0x180030125  jmp     short loc_18003015B
0x180030127  lea     rdi, aSourceid; "_SourceId"
0x18003012e  jmp     short loc_18003015B
0x180030130  lea     rdi, aUsersidstring; "_UserSidString"
0x180030137  jmp     short loc_18003015B
0x180030139  lea     rdi, aProperties; "_Properties"
0x180030140  jmp     short loc_18003015B
0x180030142  lea     rdi, aAttributes; "_Attributes"
0x180030149  jmp     short loc_18003015B
0x18003014b  lea     rdi, aCategories; "_Categories"
0x180030152  jmp     short loc_18003015B
0x180030154  lea     rdi, aData; "_Data"
0x18003015b  mov     ebp, [r14+24h]
0x18003015f  test    rdi, rdi
0x180030162  jnz     short loc_1800301A7
0x180030164  mov     rbx, [r14+28h]
0x180030168  lea     rcx, [rsp+0A8h+var_68]; this
0x18003016d  mov     edi, [r14+20h]
0x180030171  mov     rdx, r14; struct _GUID *
0x180030174  mov     esi, [rsi]
0x180030176  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18003017b  mov     rcx, rax; this
0x18003017e  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180030183  mov     [rsp+0A8h+var_78], ebp
0x180030187  lea     rdx, aSDTypeDValue0x; "%s,%d,type=%d,value=0x%p,size=%u"
0x18003018e  mov     [rsp+0A8h+var_80], rbx
0x180030193  mov     r8, rax
0x180030196  mov     rcx, r15; this
0x180030199  mov     dword ptr [rsp+0A8h+var_88], edi
0x18003019d  mov     r9d, esi
0x1800301a0  call    ?SetFormatString@FSString@@QEAAXPEBDZZ; FSString::SetFormatString(char const *,...)
0x1800301a5  jmp     short loc_18003021E
0x1800301a7  test    ebp, ebp
0x1800301a9  jz      short loc_1800301E7
0x1800301ab  cmp     dword ptr [r14+20h], 12h
0x1800301b0  jnz     short loc_1800301E7
0x1800301b2  mov     rbx, [r14+28h]
0x1800301b6  lea     rcx, [rsp+0A8h+var_68]; this
0x1800301bb  mov     rdx, r14; struct _GUID *
0x1800301be  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800301c3  mov     rcx, rax; this
0x1800301c6  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800301cb  mov     r8, rax
0x1800301ce  mov     [rsp+0A8h+var_88], rbx
0x1800301d3  mov     rcx, r15; this
0x1800301d6  lea     rdx, aSSValueWs; "%s%s,value=%ws"
0x1800301dd  mov     r9, rdi
0x1800301e0  call    ?SetFormatString@FSString@@QEAAXPEBDZZ; FSString::SetFormatString(char const *,...)
0x1800301e5  jmp     short loc_18003021E
0x1800301e7  mov     rbx, [r14+28h]
0x1800301eb  lea     rcx, [rsp+0A8h+var_68]; this
0x1800301f0  mov     rdx, r14; struct _GUID *
0x1800301f3  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800301f8  mov     rcx, rax; this
0x1800301fb  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180030200  mov     r8, rax
0x180030203  mov     dword ptr [rsp+0A8h+var_80], ebp
0x180030207  mov     rcx, r15; this
0x18003020a  mov     [rsp+0A8h+var_88], rbx
0x18003020f  mov     r9, rdi
0x180030212  lea     rdx, aSSValue0xPSize; "%s%s,value=0x%p,size=%u"
0x180030219  call    ?SetFormatString@FSString@@QEAAXPEBDZZ; FSString::SetFormatString(char const *,...)
0x18003021e  lea     rcx, [rsp+0A8h+var_68]; this
0x180030223  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180030228  mov     rcx, [rsp+0A8h+var_38]
0x18003022d  xor     rcx, rsp; StackCookie
0x180030230  call    __security_check_cookie
0x180030235  mov     rbx, [rsp+0A8h+arg_10]
0x18003023d  add     rsp, 80h
0x180030244  pop     r15
0x180030246  pop     r14
0x180030248  pop     rdi
0x180030249  pop     rsi
0x18003024a  pop     rbp
0x18003024b  retn
```
