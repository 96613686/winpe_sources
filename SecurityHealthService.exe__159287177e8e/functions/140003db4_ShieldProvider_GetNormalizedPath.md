# ShieldProvider::GetNormalizedPath

- ea: `0x140003db4`
- end: `0x140003e52`
- name: `ShieldProvider::GetNormalizedPath`
- size: `158`
- prototype: `__int64 __fastcall(unsigned __int16 **, void **, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140003e58`
- `0x140004588`

## callees

- `0x1400015f4`
- `0x140003640`
- `0x140003db4`
- `0x14000f3ac`
- `0x1400100bc`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetNormalizedPath(unsigned __int16 **a1, void **a2, const unsigned __int16 *a3)
{
  bool v3; // zf
  int v5; // eax
  unsigned __int64 v6; // rdx
  unsigned int v7; // ebx
  void *v9; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(_WORD *)a1 == 92;
  v9 = 0;
  if ( v3 )
    v5 = CommonUtil::HrDuplicateStringW((CommonUtil *)&v9, a1, a3);
  else
    v5 = CommonUtil::NewSprintfW((CommonUtil *)&v9, (unsigned __int16 **)L"\\\\?\\%s", (const unsigned __int16 *)a1);
  v7 = v5;
  if ( v5 >= 0 )
  {
    *a2 = v9;
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids,
        (unsigned int)v5);
    if ( v9 )
      operator delete(v9, v6);
    return v7;
  }
}

```

## disassembly

```asm
0x140003db4  mov     [rsp+arg_8], rbx
0x140003db9  push    rdi
0x140003dba  sub     rsp, 20h
0x140003dbe  cmp     word ptr [rcx], 5Ch ; '\'
0x140003dc2  mov     rdi, rdx
0x140003dc5  mov     [rsp+28h+arg_0], 0
0x140003dce  jnz     short loc_140003DDF
0x140003dd0  mov     rdx, rcx; unsigned __int16 **
0x140003dd3  lea     rcx, [rsp+28h+arg_0]; this
0x140003dd8  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x140003ddd  jmp     short loc_140003DF3
0x140003ddf  mov     r8, rcx; unsigned __int16 *
0x140003de2  lea     rdx, aS; "\\\\?\\%s"
0x140003de9  lea     rcx, [rsp+28h+arg_0]; this
0x140003dee  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x140003df3  mov     ebx, eax
0x140003df5  test    eax, eax
0x140003df7  jns     short loc_140003E3D
0x140003df9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003e00  lea     rax, WPP_GLOBAL_Control
0x140003e07  cmp     rcx, rax
0x140003e0a  jz      short loc_140003E2A
0x140003e0c  test    byte ptr [rcx+1Ch], 1
0x140003e10  jz      short loc_140003E2A
0x140003e12  mov     rcx, [rcx+10h]
0x140003e16  lea     r8, WPP_3783b520dcb33a570fe0d0816a6b0317_Traceguids
0x140003e1d  mov     edx, 0Ah
0x140003e22  mov     r9d, ebx
0x140003e25  call    WPP_SF_d
0x140003e2a  mov     rcx, [rsp+28h+arg_0]; void *
0x140003e2f  test    rcx, rcx
0x140003e32  jz      short loc_140003E39
0x140003e34  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140003e39  mov     eax, ebx
0x140003e3b  jmp     short loc_140003E47
0x140003e3d  mov     rax, [rsp+28h+arg_0]
0x140003e42  mov     [rdi], rax
0x140003e45  xor     eax, eax
0x140003e47  mov     rbx, [rsp+28h+arg_8]
0x140003e4c  add     rsp, 20h
0x140003e50  pop     rdi
0x140003e51  retn
```
