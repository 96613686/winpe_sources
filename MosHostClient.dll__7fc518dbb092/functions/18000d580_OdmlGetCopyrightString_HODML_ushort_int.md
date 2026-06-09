# OdmlGetCopyrightString(HODML__ *,ushort * *,int *)

- ea: `0x18000d580`
- end: `0x18000d5d7`
- name: `?OdmlGetCopyrightString@@YAJPEAUHODML__@@PEAPEAGPEAH@Z`
- size: `87`
- prototype: `__int64 __fastcall(struct HODML__ *, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008abc`
- `0x18000d580`

## pseudocode

```c
__int64 __fastcall OdmlGetCopyrightString(struct HODML__ *a1, unsigned __int16 **a2, int *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct HODML__ *v8; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 **v9; // [rsp+38h] [rbp+10h] BYREF
  int *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  v8 = a1;
  v3 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short * *,int *),void * &,unsigned short * * &,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))OdmlSvcGetCopyrightString,
         &v8,
         &v9,
         &v10);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC2,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000d580  mov     rax, rsp
0x18000d583  mov     [rax+18h], r8
0x18000d587  mov     [rax+10h], rdx
0x18000d58b  push    rbx; int
0x18000d58c  sub     rsp, 20h
0x18000d590  mov     [rax+8], rcx
0x18000d594  lea     r9, [rax+18h]
0x18000d598  lea     rcx, OdmlSvcGetCopyrightString
0x18000d59f  lea     r8, [rax+10h]
0x18000d5a3  lea     rdx, [rax+8]
0x18000d5a7  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAPEAGPEAH@ZAEAPEAXAEAPEAPEAGAEAPEAH@wil@@YAJA6AJPEAXPEAPEAGPEAH@ZAEAPEAXAEAPEAPEAGAEAPEAH@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort * *,int *),void * &,ushort * * &,int * &>(long (&)(void *,ushort * *,int *),void * &,ushort * * &,int * &)
0x18000d5ac  mov     ebx, eax
0x18000d5ae  test    eax, eax
0x18000d5b0  jns     short loc_18000D5CF
0x18000d5b2  mov     rcx, [rsp+28h]; this
0x18000d5b7  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d5be  mov     r9d, eax; char *
0x18000d5c1  mov     edx, 0C2h; void *
0x18000d5c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d5cb  mov     eax, ebx
0x18000d5cd  jmp     short loc_18000D5D1
0x18000d5cf  xor     eax, eax
0x18000d5d1  add     rsp, 20h
0x18000d5d5  pop     rbx
0x18000d5d6  retn
```
