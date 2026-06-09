# AppxAllUserStore::AutoRegLoadHive::RegLoadHive(HKEY__ * const,ushort const *,ushort const *)

- ea: `0x1800340d8`
- end: `0x18003420d`
- name: `?RegLoadHive@AutoRegLoadHive@AppxAllUserStore@@QEAAJQEAUHKEY__@@PEBG1@Z`
- size: `309`
- prototype: `int(AppxAllUserStore::AutoRegLoadHive *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800334f4`
- `0x18004252c`

## callees

- `0x180004920`
- `0x180008db0`
- `0x180018248`
- `0x18001a6a0`
- `0x1800340d8`
- `0x1800364d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180034191`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x180034191`

## string_xrefs

- `0x180034100`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x180034166`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x1800341af`: `onecore\admin\appmodel\appxalluserstore\src\CommonUtilities.hpp`
- `0x1800341a3`: `Alias %ws Path %ws.`

## pseudocode

```c
__int64 __fastcall AppxAllUserStore::AutoRegLoadHive::RegLoadHive(
        AppxAllUserStore::AutoRegLoadHive *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rdx
  unsigned int v8; // ebx
  unsigned int KeyW; // eax
  __int64 v10; // rax
  int v12; // [rsp+20h] [rbp-68h]
  __int128 v13; // [rsp+40h] [rbp-48h] BYREF
  int v14; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a3 )
  {
    v7 = 32;
LABEL_3:
    v8 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)v8,
      v12);
    return v8;
  }
  if ( !a4 )
  {
    v7 = 33;
    goto LABEL_3;
  }
  if ( *((_QWORD *)this + 1) )
  {
    v8 = -2147019873;
    v7 = 35;
    goto LABEL_4;
  }
  v14 = 0;
  v13 = 0;
  v8 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v13, a3);
  if ( (v8 & 0x80000000) == 0 )
  {
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, a3, a4);
    if ( KeyW )
    {
      v8 = wil::details::in1diag3::Return_Win32Msg(
             retaddr,
             (void *)0x28,
             (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
             (const char *)KeyW,
             (unsigned int)"Alias %ws Path %ws.",
             (const char *)a3,
             a4);
    }
    else
    {
      v10 = *((_QWORD *)&v13 + 1);
      *(_QWORD *)this = -2147483646;
      v8 = 0;
      *((_QWORD *)this + 1) = v10;
      *((_QWORD *)&v13 + 1) = 0;
      LODWORD(v13) = 0;
      v14 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x26,
      (unsigned int)"onecore\\admin\\appmodel\\appxalluserstore\\src\\CommonUtilities.hpp",
      (const char *)v8,
      (int)"Alias %ws.",
      (const char *)a3);
  }
  Common::StringBuffer::~StringBuffer((Common::StringBuffer *)&v13);
  return v8;
}

```

## disassembly

```asm
0x1800340d8  push    rbx
0x1800340da  push    rbp
0x1800340db  push    rsi
0x1800340dc  push    rdi
0x1800340dd  sub     rsp, 68h
0x1800340e1  mov     rbp, r9
0x1800340e4  mov     rdi, r8
0x1800340e7  mov     rsi, rcx
0x1800340ea  test    r8, r8
0x1800340ed  jnz     short loc_180034114
0x1800340ef  lea     edx, [r8+20h]; void *
0x1800340f3  mov     ebx, 80070057h
0x1800340f8  mov     rcx, [rsp+88h]; this
0x180034100  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x180034107  mov     r9d, ebx; char *
0x18003410a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003410f  jmp     loc_180034202
0x180034114  test    rbp, rbp
0x180034117  jnz     short loc_18003411E
0x180034119  lea     edx, [rbp+21h]
0x18003411c  jmp     short loc_1800340F3
0x18003411e  cmp     qword ptr [rcx+8], 0
0x180034123  jz      short loc_180034131
0x180034125  mov     ebx, 8007139Fh
0x18003412a  mov     edx, 23h ; '#'
0x18003412f  jmp     short loc_1800340F8
0x180034131  xor     eax, eax
0x180034133  lea     rcx, [rsp+88h+var_48]; this
0x180034138  xorps   xmm0, xmm0
0x18003413b  mov     [rsp+88h+var_38], eax
0x18003413f  mov     rdx, rdi; Src
0x180034142  movups  [rsp+88h+var_48], xmm0
0x180034147  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18003414c  mov     ebx, eax
0x18003414e  test    eax, eax
0x180034150  jns     short loc_180034181
0x180034152  mov     rcx, [rsp+88h]; this
0x18003415a  lea     rax, aAliasWs; "Alias %ws."
0x180034161  mov     [rsp+88h+var_60], rdi; char *
0x180034166  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x18003416d  mov     r9d, ebx; char *
0x180034170  mov     qword ptr [rsp+88h+var_68], rax; int
0x180034175  mov     edx, 26h ; '&'; void *
0x18003417a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003417f  jmp     short loc_1800341F8
0x180034181  mov     rbx, 0FFFFFFFF80000002h
0x180034188  mov     r8, rbp; lpFile
0x18003418b  mov     rcx, rbx; hKey
0x18003418e  mov     rdx, rdi; lpSubKey
0x180034191  call    cs:__imp_RegLoadKeyW
0x180034197  test    eax, eax
0x180034199  jz      short loc_1800341D1
0x18003419b  mov     rcx, [rsp+88h]; this
0x1800341a3  lea     rdx, aAliasWsPathWs; "Alias %ws Path %ws."
0x1800341aa  mov     [rsp+88h+var_58], rbp
0x1800341af  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\appxalluserst"...
0x1800341b6  mov     [rsp+88h+var_60], rdi; char *
0x1800341bb  mov     r9d, eax; char *
0x1800341be  mov     qword ptr [rsp+88h+var_68], rdx; unsigned int
0x1800341c3  mov     edx, 28h ; '('; void *
0x1800341c8  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800341cd  mov     ebx, eax
0x1800341cf  jmp     short loc_1800341F8
0x1800341d1  mov     rax, qword ptr [rsp+88h+var_48+8]
0x1800341d6  mov     [rsi], rbx
0x1800341d9  xor     ebx, ebx
0x1800341db  mov     [rsi+8], rax
0x1800341df  mov     qword ptr [rsp+88h+var_48+8], 0
0x1800341e8  mov     dword ptr [rsp+88h+var_48], 0
0x1800341f0  mov     [rsp+88h+var_38], 0
0x1800341f8  lea     rcx, [rsp+88h+var_48]; this
0x1800341fd  call    ??1StringBuffer@Common@@QEAA@XZ; Common::StringBuffer::~StringBuffer(void)
0x180034202  mov     eax, ebx
0x180034204  add     rsp, 68h
0x180034208  pop     rdi
0x180034209  pop     rsi
0x18003420a  pop     rbp
0x18003420b  pop     rbx
0x18003420c  retn
```
