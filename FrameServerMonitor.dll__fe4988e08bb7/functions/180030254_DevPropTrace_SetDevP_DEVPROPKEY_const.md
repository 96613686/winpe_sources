# DevPropTrace::SetDevP(_DEVPROPKEY const &)

- ea: `0x180030254`
- end: `0x180030370`
- name: `?SetDevP@DevPropTrace@@QEAAXAEBU_DEVPROPKEY@@@Z`
- size: `284`
- prototype: `void __fastcall(DevPropTrace *__hidden this, const struct _DEVPROPKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config`

## callers

- `0x18001ec2c`

## callees

- `0x180011438`
- `0x18002fa3c`
- `0x18002fa98`
- `0x18002fd04`
- `0x180030254`

## string_xrefs

- `0x180030309`: `_UserSidString`
- `0x1800302f7`: `_SymbolicName`
- `0x1800302e5`: `_RegistryBlob`

## pseudocode

```c
void __fastcall DevPropTrace::SetDevP(DevPropTrace *this, const struct _DEVPROPKEY *a2)
{
  __int64 v3; // rax
  DEVPROPID pid; // ebx
  GuidTrace *v5; // rax
  const char *v6; // rax
  const struct std::nothrow_t *v7; // rdx
  const char *v8; // rbx
  GuidTrace *v9; // rax
  const char *String; // rax
  _BYTE v11[40]; // [rsp+20h] [rbp-28h] BYREF

  v3 = *(_QWORD *)&a2->fmtid.Data1 - 0x4BD03393B3E34238LL;
  if ( *(_QWORD *)&a2->fmtid.Data1 == 0x4BD03393B3E34238LL )
    v3 = *(_QWORD *)a2->fmtid.Data4 + 0xE43CD6123C60353LL;
  if ( v3 )
    goto LABEL_13;
  switch ( a2->pid )
  {
    case 3u:
      v8 = "_Data";
      goto LABEL_23;
    case 4u:
      v8 = "_Categories";
      goto LABEL_23;
    case 5u:
      v8 = "_Attributes";
      goto LABEL_23;
    case 6u:
      v8 = "_Properties";
      goto LABEL_23;
    case 7u:
      v8 = "_UserSidString";
      goto LABEL_23;
    case 8u:
      v8 = "_SourceId";
      goto LABEL_23;
    case 9u:
      v8 = "_SymbolicName";
      goto LABEL_23;
    case 0xAu:
      v8 = "_InternalAlias";
      goto LABEL_23;
    case 0xBu:
      v8 = "_RegistryBlob";
LABEL_23:
      v9 = GuidTrace::GuidTrace((GuidTrace *)v11, &a2->fmtid);
      String = GuidTrace::GetString(v9);
      FSString::SetFormatString(this, "%s%s", String, v8);
      goto LABEL_24;
  }
LABEL_13:
  pid = a2->pid;
  v5 = GuidTrace::GuidTrace((GuidTrace *)v11, &a2->fmtid);
  v6 = GuidTrace::GetString(v5);
  FSString::SetFormatString(this, "%s,%d", v6, pid);
LABEL_24:
  FSString::~FSString((FSString *)v11, v7);
}

```

## disassembly

```asm
0x180030254  mov     [rsp+arg_0], rbx
0x180030259  push    rdi
0x18003025a  sub     rsp, 40h
0x18003025e  mov     rax, [rdx]
0x180030261  mov     rdi, rcx
0x180030264  sub     rax, cs:qword_1800557C8
0x18003026b  jnz     short loc_180030278
0x18003026d  mov     rax, [rdx+8]
0x180030271  sub     rax, cs:qword_1800557D0
0x180030278  test    rax, rax
0x18003027b  jnz     short loc_1800302B9
0x18003027d  mov     ecx, [rdx+10h]
0x180030280  sub     ecx, 3
0x180030283  jz      loc_18003032D
0x180030289  sub     ecx, 1
0x18003028c  jz      loc_180030324
0x180030292  sub     ecx, 1
0x180030295  jz      loc_18003031B
0x18003029b  sub     ecx, 1
0x18003029e  jz      short loc_180030312
0x1800302a0  sub     ecx, 1
0x1800302a3  jz      short loc_180030309
0x1800302a5  sub     ecx, 1
0x1800302a8  jz      short loc_180030300
0x1800302aa  sub     ecx, 1
0x1800302ad  jz      short loc_1800302F7
0x1800302af  sub     ecx, 1
0x1800302b2  jz      short loc_1800302EE
0x1800302b4  cmp     ecx, 1
0x1800302b7  jz      short loc_1800302E5
0x1800302b9  mov     ebx, [rdx+10h]
0x1800302bc  lea     rcx, [rsp+48h+var_28]; this
0x1800302c1  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800302c6  mov     rcx, rax; this
0x1800302c9  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800302ce  mov     r8, rax
0x1800302d1  lea     rdx, aSD; "%s,%d"
0x1800302d8  mov     rcx, rdi; this
0x1800302db  mov     r9d, ebx
0x1800302de  call    ?SetFormatString@FSString@@QEAAXPEBDZZ; FSString::SetFormatString(char const *,...)
0x1800302e3  jmp     short loc_18003035B
0x1800302e5  lea     rbx, aRegistryblob; "_RegistryBlob"
0x1800302ec  jmp     short loc_180030334
0x1800302ee  lea     rbx, aInternalalias; "_InternalAlias"
0x1800302f5  jmp     short loc_180030334
0x1800302f7  lea     rbx, aSymbolicname; "_SymbolicName"
0x1800302fe  jmp     short loc_180030334
0x180030300  lea     rbx, aSourceid; "_SourceId"
0x180030307  jmp     short loc_180030334
0x180030309  lea     rbx, aUsersidstring; "_UserSidString"
0x180030310  jmp     short loc_180030334
0x180030312  lea     rbx, aProperties; "_Properties"
0x180030319  jmp     short loc_180030334
0x18003031b  lea     rbx, aAttributes; "_Attributes"
0x180030322  jmp     short loc_180030334
0x180030324  lea     rbx, aCategories; "_Categories"
0x18003032b  jmp     short loc_180030334
0x18003032d  lea     rbx, aData; "_Data"
0x180030334  lea     rcx, [rsp+48h+var_28]; this
0x180030339  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18003033e  mov     rcx, rax; this
0x180030341  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180030346  mov     r8, rax
0x180030349  lea     rdx, aSS_0; "%s%s"
0x180030350  mov     rcx, rdi; this
0x180030353  mov     r9, rbx
0x180030356  call    ?SetFormatString@FSString@@QEAAXPEBDZZ; FSString::SetFormatString(char const *,...)
0x18003035b  lea     rcx, [rsp+48h+var_28]; this
0x180030360  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180030365  mov     rbx, [rsp+48h+arg_0]
0x18003036a  add     rsp, 40h
0x18003036e  pop     rdi
0x18003036f  retn
```
