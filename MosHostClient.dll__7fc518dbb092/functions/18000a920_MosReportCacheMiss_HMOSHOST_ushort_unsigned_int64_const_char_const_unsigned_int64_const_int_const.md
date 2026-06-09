# MosReportCacheMiss(HMOSHOST__ *,ushort,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const)

- ea: `0x18000a920`
- end: `0x18000a9bf`
- name: `?MosReportCacheMiss@@YAJPEAUHMOSHOST__@@GQEA_KQEAD1QEAH@Z`
- size: `159`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, unsigned __int16, unsigned __int64 *const, char *const, unsigned __int64 *const, int *const)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x1800086ec`
- `0x18000a920`

## pseudocode

```c
__int64 __fastcall MosReportCacheMiss(
        struct HMOSHOST__ *a1,
        unsigned __int16 a2,
        unsigned __int64 *const a3,
        char *const a4,
        unsigned __int64 *const a5,
        int *const a6)
{
  int v6; // ebx
  __int64 v7; // rdx
  int v9; // [rsp+20h] [rbp-38h]
  struct HMOSHOST__ *v10; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int16 v12; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int64 *v13; // [rsp+70h] [rbp+18h] BYREF
  char *v14; // [rsp+78h] [rbp+20h] BYREF

  v14 = a4;
  v13 = a3;
  v12 = a2;
  if ( a2 > 0x10u )
  {
    v6 = -2147024809;
    v7 = 159;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v6,
      v9);
    return (unsigned int)v6;
  }
  if ( !a1 )
  {
    v6 = -2147467261;
    v7 = 160;
    goto LABEL_3;
  }
  v10 = a1;
  v6 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,unsigned short &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &>(
         (__int64)a1,
         (int)&v10,
         (int)&v12,
         (int)&v13,
         (__int64)&v14,
         (__int64)&a5,
         (__int64)&a6);
  if ( v6 < 0 )
  {
    v7 = 166;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a920  mov     [rsp+arg_18], r9
0x18000a925  mov     [rsp+arg_10], r8
0x18000a92a  mov     [rsp+arg_8], dx
0x18000a92f  push    rbx
0x18000a930  sub     rsp, 50h
0x18000a934  cmp     dx, 10h
0x18000a938  jbe     short loc_18000A95C
0x18000a93a  mov     ebx, 80070057h
0x18000a93f  mov     edx, 9Fh; void *
0x18000a944  mov     rcx, [rsp+58h]; this
0x18000a949  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a950  mov     r9d, ebx; char *
0x18000a953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a958  mov     eax, ebx
0x18000a95a  jmp     short loc_18000A9B9
0x18000a95c  test    rcx, rcx
0x18000a95f  jnz     short loc_18000A96D
0x18000a961  mov     ebx, 80004003h
0x18000a966  mov     edx, 0A0h
0x18000a96b  jmp     short loc_18000A944
0x18000a96d  lea     rax, [rsp+58h+arg_28]
0x18000a975  mov     [rsp+58h+var_18], rcx
0x18000a97a  mov     [rsp+58h+var_28], rax
0x18000a97f  lea     r9, [rsp+58h+arg_10]
0x18000a984  lea     rax, [rsp+58h+arg_20]
0x18000a98c  mov     [rsp+58h+var_30], rax
0x18000a991  lea     r8, [rsp+58h+arg_8]
0x18000a996  lea     rax, [rsp+58h+arg_18]
0x18000a99b  lea     rdx, [rsp+58h+var_18]
0x18000a9a0  mov     [rsp+58h+var_38], rax
0x18000a9a5  call    ??$invoke_rpc_nothrow@A6AJPEAXGQEA_KQEAD1QEAH@ZAEAPEAXAEAGAEAQEA_KAEAQEADAEAQEA_KAEAQEAH@wil@@YAJA6AJPEAXGQEA_KQEAD1QEAH@ZAEAPEAXAEAGAEAQEA_KAEAQEAD7AEAQEAH@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,ushort &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &>(long (&)(void *,ushort,unsigned __int64 * const,char * const,unsigned __int64 * const,int * const),void * &,ushort &,unsigned __int64 * &,char * &,unsigned __int64 * &,int * &)
0x18000a9aa  mov     ebx, eax
0x18000a9ac  test    eax, eax
0x18000a9ae  jns     short loc_18000A9B7
0x18000a9b0  mov     edx, 0A6h
0x18000a9b5  jmp     short loc_18000A944
0x18000a9b7  xor     eax, eax
0x18000a9b9  add     rsp, 50h
0x18000a9bd  pop     rbx
0x18000a9be  retn
```
