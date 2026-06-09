# wil::details::functor_wrapper_void__lambda_93208eb893f380cc48155d176decd6a1___::Run

- ea: `0x18002e450`
- end: `0x18002e60b`
- name: `wil::details::functor_wrapper_void__lambda_93208eb893f380cc48155d176decd6a1___::Run`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002c1d0`

## callees

- `0x1800034a0`
- `0x180010cac`
- `0x1800110fc`
- `0x180011194`
- `0x18002e450`

## import_xrefs

- `deviceassociation!DafSelectCeremony` at `0x18002e46c`
- `deviceassociation!DafSelectCeremony` at `0x18002e46c`

## string_xrefs

- `0x18002e5f6`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
__int64 __fastcall wil::details::functor_wrapper_void__lambda_93208eb893f380cc48155d176decd6a1___::Run(__int64 a1)
{
  __int64 v1; // rbx
  int v2; // edx
  int v3; // r8d
  __int64 v4; // rcx
  bool v5; // dl
  bool v6; // dl
  unsigned int v8; // eax
  int v9; // [rsp+20h] [rbp-38h]
  int v10; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v1 = *(_QWORD *)(a1 + 8);
  **(_DWORD **)v1 = DafSelectCeremony(*(_QWORD *)(*(_QWORD *)(v1 + 8) + 2040LL), *(_QWORD *)(v1 + 8) + 160LL);
  if ( **(int **)v1 < 0 )
  {
    LOBYTE(v2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        v3,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v9,
        v10,
        76,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v8 = wil::verify_hresult<long>(**(_DWORD **)v1);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2BD,
      (int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v8,
      v9);
  }
  *(_OWORD *)(*(_QWORD *)(v1 + 8) + 360LL) = *(_OWORD *)(*(_QWORD *)(v1 + 8) + 160LL);
  v4 = *(_QWORD *)(v1 + 8);
  if ( DAF_Ceremony_JustWorks == *(_QWORD *)(v4 + 160) && *(_QWORD *)(v4 + 168) == 0x4B4D953B27A55DB2LL )
  {
    v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v3, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
    **(_DWORD **)v1 = -2147418113;
  }
  return 0;
}

```

## disassembly

```asm
0x18002e450  push    rbx
0x18002e452  sub     rsp, 50h
0x18002e456  mov     rbx, [rcx+8]
0x18002e45a  mov     rcx, [rbx+8]
0x18002e45e  lea     rdx, [rcx+0A0h]
0x18002e465  mov     rcx, [rcx+7F8h]
0x18002e46c  call    cs:__imp_DafSelectCeremony
0x18002e472  mov     rcx, [rbx]
0x18002e475  mov     [rcx], eax
0x18002e477  mov     rax, [rbx]
0x18002e47a  mov     r9d, [rax]
0x18002e47d  test    r9d, r9d
0x18002e480  js      loc_18002E588
0x18002e486  mov     rax, [rbx+8]
0x18002e48a  movups  xmm0, xmmword ptr [rax+0A0h]
0x18002e491  movdqu  xmmword ptr [rax+168h], xmm0
0x18002e499  mov     rcx, [rbx+8]
0x18002e49d  mov     rax, cs:DAF_Ceremony_JustWorks
0x18002e4a4  cmp     rax, [rcx+0A0h]
0x18002e4ab  jnz     short loc_18002E51D
0x18002e4ad  mov     rax, cs:qword_18003C1D0
0x18002e4b4  cmp     rax, [rcx+0A8h]
0x18002e4bb  jnz     short loc_18002E51D
0x18002e4bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e4c4  lea     rax, WPP_GLOBAL_Control
0x18002e4cb  cmp     rcx, rax
0x18002e4ce  jz      short loc_18002E4DA
0x18002e4d0  cmp     byte ptr [rcx+19h], 4
0x18002e4d4  jb      short loc_18002E4DA
0x18002e4d6  mov     dl, 1
0x18002e4d8  jmp     short loc_18002E4DC
0x18002e4da  xor     dl, dl
0x18002e4dc  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e4e3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e4ea  setnz   r8b
0x18002e4ee  test    dl, dl
0x18002e4f0  jnz     short loc_18002E4FB
0x18002e4f2  test    r8b, r8b
0x18002e4f5  jz      loc_18002E580
0x18002e4fb  mov     r9, [rcx+28h]
0x18002e4ff  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e506  mov     rcx, [rcx+10h]
0x18002e50a  mov     [rsp+58h+var_20], rax
0x18002e50f  mov     [rsp+58h+var_28], 4Dh ; 'M'
0x18002e516  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002e51b  jmp     short loc_18002E580
0x18002e51d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e524  lea     rax, WPP_GLOBAL_Control
0x18002e52b  cmp     rcx, rax
0x18002e52e  jz      short loc_18002E53A
0x18002e530  cmp     byte ptr [rcx+19h], 2
0x18002e534  jb      short loc_18002E53A
0x18002e536  mov     dl, 1
0x18002e538  jmp     short loc_18002E53C
0x18002e53a  xor     dl, dl
0x18002e53c  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e543  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e54a  setnz   r8b
0x18002e54e  test    dl, dl
0x18002e550  jnz     short loc_18002E557
0x18002e552  test    r8b, r8b
0x18002e555  jz      short loc_18002E577
0x18002e557  mov     r9, [rcx+28h]
0x18002e55b  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e562  mov     rcx, [rcx+10h]
0x18002e566  mov     [rsp+58h+var_20], rax
0x18002e56b  mov     [rsp+58h+var_28], 4Eh ; 'N'
0x18002e572  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002e577  mov     rax, [rbx]
0x18002e57a  mov     dword ptr [rax], 8000FFFFh
0x18002e580  xor     eax, eax
0x18002e582  add     rsp, 50h
0x18002e586  pop     rbx
0x18002e587  retn
0x18002e588  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e58f  lea     rax, WPP_GLOBAL_Control
0x18002e596  cmp     rcx, rax
0x18002e599  jz      short loc_18002E5A5
0x18002e59b  cmp     byte ptr [rcx+19h], 2
0x18002e59f  jb      short loc_18002E5A5
0x18002e5a1  mov     dl, 1
0x18002e5a3  jmp     short loc_18002E5A7
0x18002e5a5  xor     dl, dl
0x18002e5a7  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e5ae  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e5b5  setnz   r8b
0x18002e5b9  test    dl, dl
0x18002e5bb  jnz     short loc_18002E5C2
0x18002e5bd  test    r8b, r8b
0x18002e5c0  jz      short loc_18002E5E7
0x18002e5c2  mov     [rsp+58h+var_10], r9d
0x18002e5c7  lea     rax, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002e5ce  mov     r9, [rcx+28h]
0x18002e5d2  mov     rcx, [rcx+10h]
0x18002e5d6  mov     [rsp+58h+var_20], rax
0x18002e5db  mov     [rsp+58h+var_28], 4Ch ; 'L'
0x18002e5e2  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002e5e7  mov     rcx, [rbx]
0x18002e5ea  mov     ecx, [rcx]
0x18002e5ec  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002e5f1  mov     rcx, [rsp+58h]; this
0x18002e5f6  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002e5fd  mov     r9d, eax; char *
0x18002e600  mov     edx, 2BDh; void *
0x18002e605  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
