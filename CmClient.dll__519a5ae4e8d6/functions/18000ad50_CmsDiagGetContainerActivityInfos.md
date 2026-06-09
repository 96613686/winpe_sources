# CmsDiagGetContainerActivityInfos

- ea: `0x18000ad50`
- end: `0x18000ae59`
- name: `CmsDiagGetContainerActivityInfos`
- size: `265`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800066e4`
- `0x18000aacc`
- `0x18000ad50`
- `0x18000db50`
- `0x18000ee00`

## string_xrefs

- `0x18000adbf`: `onecore\base\gendrv\silos\clem\client\dll\diagapi.cpp`
- `0x18000ae31`: `onecore\base\gendrv\silos\clem\client\dll\diagapi.cpp`

## pseudocode

```c
__int64 __fastcall CmsDiagGetContainerActivityInfos(__int64 a1, void *a2, unsigned int *a3)
{
  int v5; // eax
  unsigned int v6; // edi
  __int64 v8; // rcx
  unsigned int v9; // eax
  void *v10; // rbx
  unsigned int *v11; // [rsp+20h] [rbp-20h] BYREF
  void **p_Src; // [rsp+28h] [rbp-18h] BYREF
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  unsigned int v15; // [rsp+70h] [rbp+30h] BYREF
  void *Src; // [rsp+78h] [rbp+38h] BYREF

  if ( a3 && (!*a3 || a2) )
  {
    v15 = 0;
    v11 = &v15;
    Src = 0;
    p_Src = &Src;
    v13 = *(_QWORD *)(a1 + 24);
    v5 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_INFO * *,unsigned long *),void *,_CMS_ACTIVITY_INFO * *,unsigned long *>(
           a1,
           &v13,
           &p_Src,
           &v11);
    v6 = v5;
    if ( v5 >= 0 )
    {
      v8 = v15;
      v9 = *a3;
      *a3 = v15;
      if ( v9 < (unsigned int)v8 )
      {
        if ( Src )
          MIDL_user_free(Src);
        return 2147942522LL;
      }
      else
      {
        v10 = Src;
        memcpy_0(a2, Src, 12 * v8);
        if ( v10 )
          MIDL_user_free(v10);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\diagapi.cpp",
        (const char *)(unsigned int)v5,
        (int)v11);
      if ( Src )
        MIDL_user_free(Src);
      return v6;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\diagapi.cpp",
      (const char *)0x80070057LL,
      (int)v11);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000ad50  mov     [rsp-18h+arg_0], rbx
0x18000ad55  push    rbp
0x18000ad56  push    rsi
0x18000ad57  push    rdi
0x18000ad58  mov     rbp, rsp
0x18000ad5b  sub     rsp, 40h
0x18000ad5f  mov     rbx, r8
0x18000ad62  mov     rsi, rdx
0x18000ad65  test    r8, r8
0x18000ad68  jz      loc_18000AE2D
0x18000ad6e  cmp     dword ptr [r8], 0
0x18000ad72  jbe     short loc_18000AD7D
0x18000ad74  test    rdx, rdx
0x18000ad77  jz      loc_18000AE2D
0x18000ad7d  lea     rax, [rbp+arg_10]
0x18000ad81  mov     [rbp+arg_10], 0
0x18000ad88  mov     [rbp+var_20], rax
0x18000ad8c  lea     r9, [rbp+var_20]
0x18000ad90  lea     rax, [rbp+Src]
0x18000ad94  mov     [rbp+Src], 0
0x18000ad9c  mov     [rbp+var_18], rax
0x18000ada0  lea     r8, [rbp+var_18]
0x18000ada4  mov     rax, [rcx+18h]
0x18000ada8  lea     rdx, [rbp+var_10]
0x18000adac  mov     [rbp+var_10], rax
0x18000adb0  call    ??$InvokeStubFunction@P6AJPEAXPEAPEAU_CMS_ACTIVITY_INFO@@PEAK@ZPEAXPEAPEAU1@PEAK@Rpc@Manager@Container@@YAJP6AJPEAXPEAPEAU_CMS_ACTIVITY_INFO@@PEAK@Z$$QEAPEAX$$QEAPEAPEAU3@$$QEAPEAK@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,_CMS_ACTIVITY_INFO * *,ulong *),void *,_CMS_ACTIVITY_INFO * *,ulong *>(long (*)(void *,_CMS_ACTIVITY_INFO * *,ulong *),void * &&,_CMS_ACTIVITY_INFO * * &&,ulong * &&)
0x18000adb5  mov     edi, eax
0x18000adb7  test    eax, eax
0x18000adb9  jns     short loc_18000ADE5
0x18000adbb  mov     rcx, [rbp+18h]; this
0x18000adbf  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000adc6  mov     r9d, eax; char *
0x18000adc9  mov     edx, 80h; void *
0x18000adce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000add3  mov     rcx, [rbp+Src]; void *
0x18000add7  test    rcx, rcx
0x18000adda  jz      short loc_18000ADE1
0x18000addc  call    MIDL_user_free
0x18000ade1  mov     eax, edi
0x18000ade3  jmp     short loc_18000AE4C
0x18000ade5  mov     ecx, [rbp+arg_10]
0x18000ade8  mov     eax, [rbx]
0x18000adea  mov     [rbx], ecx
0x18000adec  cmp     eax, ecx
0x18000adee  jb      short loc_18000AE18
0x18000adf0  mov     rbx, [rbp+Src]
0x18000adf4  lea     r8, [rcx+rcx*2]
0x18000adf8  shl     r8, 2; Size
0x18000adfc  mov     rdx, rbx; Src
0x18000adff  mov     rcx, rsi; void *
0x18000ae02  call    memcpy_0
0x18000ae07  test    rbx, rbx
0x18000ae0a  jz      short loc_18000AE14
0x18000ae0c  mov     rcx, rbx; void *
0x18000ae0f  call    MIDL_user_free
0x18000ae14  xor     eax, eax
0x18000ae16  jmp     short loc_18000AE4C
0x18000ae18  mov     rcx, [rbp+Src]; void *
0x18000ae1c  test    rcx, rcx
0x18000ae1f  jz      short loc_18000AE26
0x18000ae21  call    MIDL_user_free
0x18000ae26  mov     eax, 8007007Ah
0x18000ae2b  jmp     short loc_18000AE4C
0x18000ae2d  mov     rcx, [rbp+18h]; this
0x18000ae31  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000ae38  mov     ebx, 80070057h
0x18000ae3d  mov     edx, 73h ; 's'; void *
0x18000ae42  mov     r9d, ebx; char *
0x18000ae45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ae4a  mov     eax, ebx
0x18000ae4c  mov     rbx, [rsp+40h+arg_0]
0x18000ae51  add     rsp, 40h
0x18000ae55  pop     rdi
0x18000ae56  pop     rsi
0x18000ae57  pop     rbp
0x18000ae58  retn
```
