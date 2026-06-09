# LaunchCredUIThreadProc(void *)

- ea: `0x14000ec00`
- end: `0x14000ecf7`
- name: `?LaunchCredUIThreadProc@@YAKPEAX@Z`
- size: `247`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000e370`
- `0x14000ec00`
- `0x1400137d4`
- `0x140017f90`

## string_xrefs

- `0x14000eccb`: `shellcommon\internal\shell\inc\CredUIApiCommon.h`

## pseudocode

```c
__int64 __fastcall LaunchCredUIThreadProc(_QWORD *Parameter, __int64 a2)
{
  struct _CREDUI_INFOW *v2; // rbx
  __int64 v3; // rdi
  int v4; // esi
  __int64 v5; // rbp
  __int64 v6; // r14
  __int64 v7; // r15
  int v8; // r12d
  __int64 v9; // r13
  unsigned int v10; // eax
  HWND hwndParent; // rcx
  unsigned int v12; // ecx
  int v13; // eax
  int v15; // [rsp+20h] [rbp-88h]
  __int64 v16; // [rsp+28h] [rbp-80h]
  __int64 v17; // [rsp+48h] [rbp-60h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v19; // [rsp+B0h] [rbp+8h] BYREF
  unsigned int v20; // [rsp+B8h] [rbp+10h] BYREF
  unsigned int v21; // [rsp+C0h] [rbp+18h]
  __int64 v22; // [rsp+C8h] [rbp+20h]

  v2 = (struct _CREDUI_INFOW *)*Parameter;
  v3 = Parameter[9];
  v4 = *((_DWORD *)Parameter + 16);
  v5 = Parameter[7];
  v6 = Parameter[6];
  v7 = Parameter[5];
  v8 = *((_DWORD *)Parameter + 8);
  v9 = Parameter[3];
  v22 = Parameter[2];
  v10 = *((_DWORD *)Parameter + 2);
  v20 = 0;
  hwndParent = v2->hwndParent;
  v21 = v10;
  v19 = 0;
  if ( (int)Windows::Internal::Shell::Holographic::GetWindowDisplayContext(hwndParent, a2, &v19) < 0
    || (v12 = 1, v19 != 1) )
  {
    v12 = 0;
  }
  LODWORD(v17) = v4;
  LODWORD(v16) = v8;
  v13 = RunCredUIWithStyle(v12, v2, v21, v22, v9, v16, v7, v6, v5, v17, v3, &v20);
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\CredUIApiCommon.h",
      (const char *)(unsigned int)v13,
      v15);
  return v20;
}

```

## disassembly

```asm
0x14000ec00  mov     r11, rsp
0x14000ec03  push    rbx
0x14000ec04  push    rbp
0x14000ec05  push    rsi
0x14000ec06  push    rdi
0x14000ec07  push    r12
0x14000ec09  push    r13
0x14000ec0b  push    r14
0x14000ec0d  push    r15
0x14000ec0f  sub     rsp, 68h
0x14000ec13  mov     rax, [rcx+10h]
0x14000ec17  lea     r8, [r11+8]
0x14000ec1b  mov     rbx, [rcx]
0x14000ec1e  mov     rdi, [rcx+48h]
0x14000ec22  mov     esi, [rcx+40h]
0x14000ec25  mov     rbp, [rcx+38h]
0x14000ec29  mov     r14, [rcx+30h]
0x14000ec2d  mov     r15, [rcx+28h]
0x14000ec31  mov     r12d, [rcx+20h]
0x14000ec35  mov     r13, [rcx+18h]
0x14000ec39  mov     [rsp+0A8h+arg_18], rax
0x14000ec41  mov     eax, [rcx+8]
0x14000ec44  mov     dword ptr [r11+10h], 0
0x14000ec4c  mov     rcx, [rbx+8]
0x14000ec50  mov     [rsp+0A8h+arg_10], eax
0x14000ec57  mov     dword ptr [r11+8], 0
0x14000ec5f  call    ?GetWindowDisplayContext@Holographic@Shell@Internal@Windows@@YAJPEAUHWND__@@W4ContextInspectionOptions@1234@PEAW4UserDisplayContext@1234@@Z; Windows::Internal::Shell::Holographic::GetWindowDisplayContext(HWND__ *,Windows::Internal::Shell::Holographic::ContextInspectionOptions,Windows::Internal::Shell::Holographic::UserDisplayContext *)
0x14000ec64  test    eax, eax
0x14000ec66  js      short loc_14000EC76
0x14000ec68  mov     ecx, 1
0x14000ec6d  cmp     [rsp+0A8h+arg_0], ecx
0x14000ec74  jz      short loc_14000EC78
0x14000ec76  xor     ecx, ecx
0x14000ec78  mov     r9, [rsp+0A8h+arg_18]
0x14000ec80  lea     rax, [rsp+0A8h+arg_8]
0x14000ec88  mov     r8d, [rsp+0A8h+arg_10]
0x14000ec90  mov     rdx, rbx
0x14000ec93  mov     [rsp+0A8h+var_50], rax
0x14000ec98  mov     [rsp+0A8h+var_58], rdi
0x14000ec9d  mov     dword ptr [rsp+0A8h+var_60], esi
0x14000eca1  mov     [rsp+0A8h+var_68], rbp
0x14000eca6  mov     [rsp+0A8h+var_70], r14
0x14000ecab  mov     [rsp+0A8h+var_78], r15
0x14000ecb0  mov     dword ptr [rsp+0A8h+var_80], r12d
0x14000ecb5  mov     qword ptr [rsp+0A8h+var_88], r13; int
0x14000ecba  call    ?RunCredUIWithStyle@@YAJW4CredUIStyle@Controller@Credentials@UI@Internal@Windows@@PEAU_CREDUI_INFOW@@KPEAKPEBXKPEAPEAX2PEAHK_K2@Z; RunCredUIWithStyle(Windows::Internal::UI::Credentials::Controller::CredUIStyle,_CREDUI_INFOW *,ulong,ulong *,void const *,ulong,void * *,ulong *,int *,ulong,unsigned __int64,ulong *)
0x14000ecbf  test    eax, eax
0x14000ecc1  jns     short loc_14000ECDF
0x14000ecc3  mov     rcx, [rsp+0A8h]; this
0x14000eccb  lea     r8, aShellcommonInt; "shellcommon\\internal\\shell\\inc\\Cred"...
0x14000ecd2  mov     r9d, eax; char *
0x14000ecd5  mov     edx, 97h; void *
0x14000ecda  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000ecdf  mov     eax, [rsp+0A8h+arg_8]
0x14000ece6  add     rsp, 68h
0x14000ecea  pop     r15
0x14000ecec  pop     r14
0x14000ecee  pop     r13
0x14000ecf0  pop     r12
0x14000ecf2  pop     rdi
0x14000ecf3  pop     rsi
0x14000ecf4  pop     rbp
0x14000ecf5  pop     rbx
0x14000ecf6  retn
```
