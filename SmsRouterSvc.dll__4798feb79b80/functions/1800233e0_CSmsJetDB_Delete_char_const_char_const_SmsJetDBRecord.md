# CSmsJetDB::Delete(char const *,char const *,SmsJetDBRecord *)

- ea: `0x1800233e0`
- end: `0x180023491`
- name: `?Delete@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@@Z`
- size: `177`
- prototype: `__int64 __fastcall(CSmsJetDB *__hidden this, const char *, const char *, struct SmsJetDBRecord *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18001c538`
- `0x18001c944`
- `0x18001f378`

## callees

- `0x180003a60`
- `0x18001a1f4`
- `0x18001ae24`
- `0x18002305c`
- `0x1800233e0`
- `0x180025430`

## import_xrefs

- `ESENT!JetDelete` at `0x18002343d`
- `ESENT!JetDelete` at `0x18002343d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsJetDB::Delete(JET_SESID *this, char *a2, const char *a3, struct SmsJetDBRecord *a4)
{
  __int64 result; // rax
  unsigned int *v7; // rax
  JET_ERR v8; // ebx
  char *v9[4]; // [rsp+30h] [rbp-48h] BYREF

  result = CSmsJetDB::Seek((CSmsJetDB *)this, a2, a3, a4, 0);
  if ( (int)result >= 0 )
  {
    std::string::string(v9, a2);
    v7 = (unsigned int *)std::map<std::string,unsigned long>::operator[](this + 4, v9);
    v8 = JetDelete(this[6], *(_QWORD *)(((unsigned __int64)*v7 << 7) + this[1] + 88));
    std::string::~string(v9);
    if ( v8 >= 0 )
    {
      return 0;
    }
    else if ( v8 == -1011 )
    {
      return 2147942414LL;
    }
    else
    {
      return v8 & 0x8E5E0000 | (unsigned __int16)-(__int16)v8 | 0xE5E0000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800233e0  push    rbx
0x1800233e2  push    rdi
0x1800233e3  sub     rsp, 68h
0x1800233e7  mov     rax, cs:__security_cookie
0x1800233ee  xor     rax, rsp
0x1800233f1  mov     [rsp+78h+var_28], rax
0x1800233f6  mov     rdi, rdx
0x1800233f9  mov     rbx, rcx
0x1800233fc  mov     [rsp+78h+var_58], 0; int
0x180023404  call    ?Seek@CSmsJetDB@@QEAAJPEBD0PEAVSmsJetDBRecord@@H@Z; CSmsJetDB::Seek(char const *,char const *,SmsJetDBRecord *,int)
0x180023409  test    eax, eax
0x18002340b  js      short loc_18002347D
0x18002340d  mov     rdx, rdi
0x180023410  lea     rcx, [rsp+78h+var_48]
0x180023415  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002341a  nop
0x18002341b  lea     rcx, [rbx+20h]
0x18002341f  lea     rdx, [rsp+78h+var_48]
0x180023424  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@KU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@K@std@@@2@@std@@QEAAAEAK$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,ulong>::operator[](std::string &&)
0x180023429  mov     r8d, [rax]
0x18002342c  shl     r8, 7
0x180023430  mov     rdx, [rbx+8]
0x180023434  mov     rdx, [r8+rdx+58h]; tableid
0x180023439  mov     rcx, [rbx+30h]; sesid
0x18002343d  call    cs:__imp_JetDelete
0x180023443  mov     ebx, eax
0x180023445  lea     rcx, [rsp+78h+var_48]
0x18002344a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002344f  test    ebx, ebx
0x180023451  jns     short loc_18002347B
0x180023453  cmp     ebx, 0FFFFFC0Dh
0x180023459  jnz     short loc_180023462
0x18002345b  mov     eax, 8007000Eh
0x180023460  jmp     short loc_18002347D
0x180023462  mov     eax, ebx
0x180023464  neg     eax
0x180023466  cmovs   eax, ebx
0x180023469  movzx   eax, ax
0x18002346c  and     ebx, 8E5E0000h
0x180023472  or      eax, ebx
0x180023474  or      eax, 0E5E0000h
0x180023479  jmp     short loc_18002347D
0x18002347b  xor     eax, eax
0x18002347d  mov     rcx, [rsp+78h+var_28]
0x180023482  xor     rcx, rsp; StackCookie
0x180023485  call    __security_check_cookie
0x18002348a  add     rsp, 68h
0x18002348e  pop     rdi
0x18002348f  pop     rbx
0x180023490  retn
```
