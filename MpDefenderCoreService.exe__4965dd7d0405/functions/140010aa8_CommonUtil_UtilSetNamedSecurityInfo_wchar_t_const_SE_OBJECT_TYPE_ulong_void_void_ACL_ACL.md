# CommonUtil::UtilSetNamedSecurityInfo(wchar_t const *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)

- ea: `0x140010aa8`
- end: `0x140010b33`
- name: `?UtilSetNamedSecurityInfo@CommonUtil@@YAJPEB_WW4_SE_OBJECT_TYPE@@KPEAX2PEAU_ACL@@3@Z`
- size: `139`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, const wchar_t *, enum _SE_OBJECT_TYPE, unsigned int, void *, void *, struct _ACL *, struct _ACL *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14008a040`

## callees

- `0x140010aa8`
- `0x140085d94`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x140010ad5`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x140010ad5`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilSetNamedSecurityInfo(
        WCHAR *this,
        const wchar_t *a2,
        SECURITY_INFORMATION a3,
        void *a4,
        void *a5,
        struct _ACL *a6,
        struct _ACL *a7)
{
  int v7; // edi
  signed int v8; // eax
  unsigned int v9; // ebx

  v7 = (int)this;
  v8 = SetNamedSecurityInfoW(this, (SE_OBJECT_TYPE)a2, a3, a4, a5, a6, a7);
  if ( !v8 )
    return 0;
  v9 = (unsigned __int16)v8 | 0x80070000;
  if ( v8 <= 0 )
    v9 = v8;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      21,
      (unsigned int)WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids,
      v7,
      v9);
  return v9;
}

```

## disassembly

```asm
0x140010aa8  mov     r11, rsp
0x140010aab  mov     [r11+8], rbx
0x140010aaf  push    rdi
0x140010ab0  sub     rsp, 40h
0x140010ab4  mov     rax, [rsp+48h+arg_30]
0x140010abc  mov     rdi, rcx
0x140010abf  mov     [r11-18h], rax
0x140010ac3  mov     rax, [rsp+48h+arg_28]
0x140010ac8  mov     [r11-20h], rax
0x140010acc  mov     rax, [rsp+48h+arg_20]
0x140010ad1  mov     [r11-28h], rax
0x140010ad5  call    cs:__imp_SetNamedSecurityInfoW
0x140010adb  test    eax, eax
0x140010add  jz      short loc_140010B26
0x140010adf  movzx   ebx, ax
0x140010ae2  or      ebx, 80070000h
0x140010ae8  test    eax, eax
0x140010aea  cmovle  ebx, eax
0x140010aed  mov     rcx, cs:WPP_GLOBAL_Control
0x140010af4  lea     rax, WPP_GLOBAL_Control
0x140010afb  cmp     rcx, rax
0x140010afe  jz      short loc_140010B22
0x140010b00  test    byte ptr [rcx+1Ch], 1
0x140010b04  jz      short loc_140010B22
0x140010b06  mov     rcx, [rcx+10h]
0x140010b0a  lea     r8, WPP_75abd5b169db356f85f54582dbfea5fb_Traceguids
0x140010b11  mov     edx, 15h
0x140010b16  mov     [rsp+48h+var_28], ebx
0x140010b1a  mov     r9, rdi
0x140010b1d  call    WPP_SF_Sd
0x140010b22  mov     eax, ebx
0x140010b24  jmp     short loc_140010B28
0x140010b26  xor     eax, eax
0x140010b28  mov     rbx, [rsp+48h+arg_0]
0x140010b2d  add     rsp, 40h
0x140010b31  pop     rdi
0x140010b32  retn
```
