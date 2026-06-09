# MosGetCopyrightString(HMOSHOST__ *,ushort * *,int *)

- ea: `0x18000a200`
- end: `0x18000a26b`
- name: `?MosGetCopyrightString@@YAJPEAUHMOSHOST__@@PEAPEAGPEAH@Z`
- size: `107`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, unsigned __int16 **, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008abc`
- `0x18000a200`

## pseudocode

```c
__int64 __fastcall MosGetCopyrightString(struct HMOSHOST__ *a1, unsigned __int16 **a2, int *a3)
{
  int v3; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct HMOSHOST__ *v8; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 **v9; // [rsp+38h] [rbp+10h] BYREF
  int *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  if ( !a1 )
  {
    v3 = -2147467261;
    v4 = 505;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v3,
      v6);
    return (unsigned int)v3;
  }
  v8 = a1;
  v3 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short * *,int *),void * &,unsigned short * * &,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))MosHostGetCopyrightString,
         &v8,
         &v9,
         &v10);
  if ( v3 < 0 )
  {
    v4 = 510;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a200  mov     [rsp+arg_10], r8
0x18000a205  mov     [rsp+arg_8], rdx
0x18000a20a  push    rbx; int
0x18000a20b  sub     rsp, 20h
0x18000a20f  test    rcx, rcx
0x18000a212  jnz     short loc_18000A236
0x18000a214  mov     ebx, 80004003h
0x18000a219  mov     edx, 1F9h; void *
0x18000a21e  mov     rcx, [rsp+28h]; this
0x18000a223  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a22a  mov     r9d, ebx; char *
0x18000a22d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a232  mov     eax, ebx
0x18000a234  jmp     short loc_18000A265
0x18000a236  mov     [rsp+28h+arg_0], rcx
0x18000a23b  lea     r9, [rsp+28h+arg_10]
0x18000a240  lea     rcx, MosHostGetCopyrightString
0x18000a247  lea     r8, [rsp+28h+arg_8]
0x18000a24c  lea     rdx, [rsp+28h+arg_0]
0x18000a251  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAPEAGPEAH@ZAEAPEAXAEAPEAPEAGAEAPEAH@wil@@YAJA6AJPEAXPEAPEAGPEAH@ZAEAPEAXAEAPEAPEAGAEAPEAH@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort * *,int *),void * &,ushort * * &,int * &>(long (&)(void *,ushort * *,int *),void * &,ushort * * &,int * &)
0x18000a256  mov     ebx, eax
0x18000a258  test    eax, eax
0x18000a25a  jns     short loc_18000A263
0x18000a25c  mov     edx, 1FEh
0x18000a261  jmp     short loc_18000A21E
0x18000a263  xor     eax, eax
0x18000a265  add     rsp, 20h
0x18000a269  pop     rbx
0x18000a26a  retn
```
