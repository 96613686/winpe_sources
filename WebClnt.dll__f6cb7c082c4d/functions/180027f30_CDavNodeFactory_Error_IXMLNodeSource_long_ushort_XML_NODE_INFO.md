# CDavNodeFactory::Error(IXMLNodeSource *,long,ushort,_XML_NODE_INFO * *)

- ea: `0x180027f30`
- end: `0x1800282c1`
- name: `?Error@CDavNodeFactory@@UEAAJPEAUIXMLNodeSource@@JGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `913`
- prototype: `__int64 __fastcall(CDavNodeFactory *this, struct IXMLNodeSource *, int, unsigned __int16)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18000b7dc`
- `0x18000b81c`
- `0x18000b89c`
- `0x180027f30`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002804a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028092`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800280da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028172`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800281d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800281fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028238`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027f98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028002`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002804a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028092`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800280da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028132`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028172`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800281d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800281fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028238`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028272`
- `OLEAUT32!__imp_SysFreeString` at `0x1800282a0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800282a0`

## pseudocode

```c
__int64 __fastcall CDavNodeFactory::Error(
        CDavNodeFactory *this,
        struct IXMLNodeSource *a2,
        int a3,
        unsigned __int16 a4)
{
  int v4; // esi
  _BYTE *v7; // rax
  DWORD CurrentThreadId; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  int v11; // ebx
  DWORD v12; // eax
  int v13; // ebx
  DWORD v14; // eax
  int v15; // ebx
  DWORD v16; // eax
  int v17; // ebx
  DWORD v18; // eax
  __int64 v19; // rdx
  BSTR v20; // rbx
  DWORD v21; // eax
  _BYTE *v22; // rax
  __int64 v23; // rbx
  DWORD v24; // eax
  int v25; // ebx
  DWORD v26; // eax
  int v27; // ebx
  DWORD v28; // eax
  int v30; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  __int64 v32; // [rsp+40h] [rbp-10h] BYREF
  int v33; // [rsp+88h] [rbp+38h] BYREF

  v4 = a4;
  bstrString = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      CurrentThreadId = GetCurrentThreadId();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
        CurrentThreadId);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 != (_BYTE *)&WPP_GLOBAL_Control )
    {
      if ( (v7[28] & 8) != 0 )
      {
        v9 = GetCurrentThreadId();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v9, a3);
        v7 = WPP_GLOBAL_Control;
      }
      if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && (v7[28] & 8) != 0 )
      {
        v10 = GetCurrentThreadId();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v10, v4);
      }
    }
  }
  v11 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *))(*(_QWORD *)a2 + 48LL))(a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v12 = GetCurrentThreadId();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v12, v11);
  }
  v13 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *))(*(_QWORD *)a2 + 56LL))(a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v14 = GetCurrentThreadId();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v14, v13);
  }
  v15 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *))(*(_QWORD *)a2 + 64LL))(a2);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v16 = GetCurrentThreadId();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v16, v15);
  }
  v17 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *, BSTR *))(*(_QWORD *)a2 + 88LL))(a2, &bstrString);
  if ( v17 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v20 = bstrString;
      v21 = GetCurrentThreadId();
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
        v21,
        (__int64)v20);
    }
    v17 = (*(__int64 (__fastcall **)(struct IXMLNodeSource *, __int64 *, int *, int *))(*(_QWORD *)a2 + 72LL))(
            a2,
            &v32,
            &v33,
            &v30);
    if ( v17 >= 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          v23 = v32;
          v24 = GetCurrentThreadId();
          WPP_SF_dS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
            v24,
            v23);
          v22 = WPP_GLOBAL_Control;
        }
        if ( v22 != (_BYTE *)&WPP_GLOBAL_Control )
        {
          if ( (v22[28] & 8) != 0 )
          {
            v25 = v33;
            v26 = GetCurrentThreadId();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              25,
              WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
              v26,
              v25);
            v22 = WPP_GLOBAL_Control;
          }
          if ( v22 != (_BYTE *)&WPP_GLOBAL_Control && (v22[28] & 8) != 0 )
          {
            v27 = v30;
            v28 = GetCurrentThreadId();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids,
              v28,
              v27);
          }
        }
      }
      if ( bstrString )
        SysFreeString(bstrString);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v18 = GetCurrentThreadId();
      v19 = 23;
      goto LABEL_23;
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v18 = GetCurrentThreadId();
    v19 = 21;
LABEL_23:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids, v18, v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180027f30  mov     [rsp-28h+arg_0], rbx
0x180027f35  mov     [rsp-28h+arg_10], rsi
0x180027f3a  push    rbp
0x180027f3b  push    rdi
0x180027f3c  push    r12
0x180027f3e  push    r14
0x180027f40  push    r15
0x180027f42  mov     rbp, rsp
0x180027f45  sub     rsp, 50h
0x180027f49  movzx   esi, r9w
0x180027f4d  mov     ebx, r8d
0x180027f50  mov     rdi, rdx
0x180027f53  mov     [rbp+bstrString], 0
0x180027f5b  mov     [rbp+var_10], 0
0x180027f63  mov     [rbp+arg_8], 0
0x180027f6a  mov     [rbp+var_20], 0
0x180027f71  mov     rax, cs:WPP_GLOBAL_Control
0x180027f78  lea     r15, WPP_GLOBAL_Control
0x180027f7f  lea     r12, WPP_6dbd170b9ddf3d549aad60b0e196052c_Traceguids
0x180027f86  mov     r14b, 8
0x180027f89  cmp     rax, r15
0x180027f8c  jz      loc_180028027
0x180027f92  test    [rax+1Ch], r14b
0x180027f96  jz      short loc_180027FC0
0x180027f98  call    cs:__imp_GetCurrentThreadId
0x180027f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fa5  mov     edx, 0Fh
0x180027faa  mov     r9d, eax
0x180027fad  mov     r8, r12
0x180027fb0  mov     rcx, [rcx+10h]
0x180027fb4  call    WPP_SF_d
0x180027fb9  mov     rax, cs:WPP_GLOBAL_Control
0x180027fc0  cmp     rax, r15
0x180027fc3  jz      short loc_180028027
0x180027fc5  test    [rax+1Ch], r14b
0x180027fc9  jz      short loc_180027FF7
0x180027fcb  call    cs:__imp_GetCurrentThreadId
0x180027fd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fd8  mov     edx, 10h
0x180027fdd  mov     r9d, eax
0x180027fe0  mov     dword ptr [rsp+50h+var_30], ebx
0x180027fe4  mov     r8, r12
0x180027fe7  mov     rcx, [rcx+10h]
0x180027feb  call    WPP_SF_Dd
0x180027ff0  mov     rax, cs:WPP_GLOBAL_Control
0x180027ff7  cmp     rax, r15
0x180027ffa  jz      short loc_180028027
0x180027ffc  test    [rax+1Ch], r14b
0x180028000  jz      short loc_180028027
0x180028002  call    cs:__imp_GetCurrentThreadId
0x180028008  mov     rcx, cs:WPP_GLOBAL_Control
0x18002800f  mov     edx, 11h
0x180028014  mov     r9d, eax
0x180028017  mov     dword ptr [rsp+50h+var_30], esi
0x18002801b  mov     r8, r12
0x18002801e  mov     rcx, [rcx+10h]
0x180028022  call    WPP_SF_Dd
0x180028027  mov     rax, [rdi]
0x18002802a  mov     rcx, rdi
0x18002802d  mov     rax, [rax+30h]
0x180028031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028036  mov     ebx, eax
0x180028038  mov     rcx, cs:WPP_GLOBAL_Control
0x18002803f  cmp     rcx, r15
0x180028042  jz      short loc_18002806F
0x180028044  test    [rcx+1Ch], r14b
0x180028048  jz      short loc_18002806F
0x18002804a  call    cs:__imp_GetCurrentThreadId
0x180028050  mov     rcx, cs:WPP_GLOBAL_Control
0x180028057  mov     edx, 12h
0x18002805c  mov     r9d, eax
0x18002805f  mov     dword ptr [rsp+50h+var_30], ebx
0x180028063  mov     r8, r12
0x180028066  mov     rcx, [rcx+10h]
0x18002806a  call    WPP_SF_Dd
0x18002806f  mov     rax, [rdi]
0x180028072  mov     rcx, rdi
0x180028075  mov     rax, [rax+38h]
0x180028079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002807e  mov     ebx, eax
0x180028080  mov     rcx, cs:WPP_GLOBAL_Control
0x180028087  cmp     rcx, r15
0x18002808a  jz      short loc_1800280B7
0x18002808c  test    [rcx+1Ch], r14b
0x180028090  jz      short loc_1800280B7
0x180028092  call    cs:__imp_GetCurrentThreadId
0x180028098  mov     rcx, cs:WPP_GLOBAL_Control
0x18002809f  mov     edx, 13h
0x1800280a4  mov     r9d, eax
0x1800280a7  mov     dword ptr [rsp+50h+var_30], ebx
0x1800280ab  mov     r8, r12
0x1800280ae  mov     rcx, [rcx+10h]
0x1800280b2  call    WPP_SF_Dd
0x1800280b7  mov     rax, [rdi]
0x1800280ba  mov     rcx, rdi
0x1800280bd  mov     rax, [rax+40h]
0x1800280c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280c6  mov     ebx, eax
0x1800280c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280cf  cmp     rcx, r15
0x1800280d2  jz      short loc_1800280FF
0x1800280d4  test    [rcx+1Ch], r14b
0x1800280d8  jz      short loc_1800280FF
0x1800280da  call    cs:__imp_GetCurrentThreadId
0x1800280e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800280e7  mov     edx, 14h
0x1800280ec  mov     r9d, eax
0x1800280ef  mov     dword ptr [rsp+50h+var_30], ebx
0x1800280f3  mov     r8, r12
0x1800280f6  mov     rcx, [rcx+10h]
0x1800280fa  call    WPP_SF_Dd
0x1800280ff  mov     rax, [rdi]
0x180028102  lea     rdx, [rbp+bstrString]
0x180028106  mov     rcx, rdi
0x180028109  mov     rax, [rax+58h]
0x18002810d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028112  mov     ebx, eax
0x180028114  test    eax, eax
0x180028116  jns     short loc_18002815C
0x180028118  mov     rcx, cs:WPP_GLOBAL_Control
0x18002811f  cmp     rcx, r15
0x180028122  jz      loc_1800282A6
0x180028128  test    [rcx+1Ch], r14b
0x18002812c  jz      loc_1800282A6
0x180028132  call    cs:__imp_GetCurrentThreadId
0x180028138  mov     edx, 15h
0x18002813d  mov     rcx, cs:WPP_GLOBAL_Control
0x180028144  mov     r9d, eax
0x180028147  mov     r8, r12
0x18002814a  mov     dword ptr [rsp+50h+var_30], ebx
0x18002814e  mov     rcx, [rcx+10h]
0x180028152  call    WPP_SF_Dd
0x180028157  jmp     loc_1800282A6
0x18002815c  mov     rax, cs:WPP_GLOBAL_Control
0x180028163  cmp     rax, r15
0x180028166  jz      short loc_180028198
0x180028168  test    [rax+1Ch], r14b
0x18002816c  jz      short loc_180028198
0x18002816e  mov     rbx, [rbp+bstrString]
0x180028172  call    cs:__imp_GetCurrentThreadId
0x180028178  mov     rcx, cs:WPP_GLOBAL_Control
0x18002817f  mov     edx, 16h
0x180028184  mov     r9d, eax
0x180028187  mov     [rsp+50h+var_30], rbx
0x18002818c  mov     r8, r12
0x18002818f  mov     rcx, [rcx+10h]
0x180028193  call    WPP_SF_dS
0x180028198  mov     rax, [rdi]
0x18002819b  lea     r9, [rbp+var_20]
0x18002819f  lea     r8, [rbp+arg_8]
0x1800281a3  mov     rcx, rdi
0x1800281a6  lea     rdx, [rbp+var_10]
0x1800281aa  mov     rax, [rax+48h]
0x1800281ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281b3  mov     ebx, eax
0x1800281b5  test    eax, eax
0x1800281b7  jns     short loc_1800281E3
0x1800281b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281c0  cmp     rcx, r15
0x1800281c3  jz      loc_1800282A6
0x1800281c9  test    [rcx+1Ch], r14b
0x1800281cd  jz      loc_1800282A6
0x1800281d3  call    cs:__imp_GetCurrentThreadId
0x1800281d9  mov     edx, 17h
0x1800281de  jmp     loc_18002813D
0x1800281e3  mov     rax, cs:WPP_GLOBAL_Control
0x1800281ea  cmp     rax, r15
0x1800281ed  jz      loc_180028297
0x1800281f3  test    [rax+1Ch], r14b
0x1800281f7  jz      short loc_18002822A
0x1800281f9  mov     rbx, [rbp+var_10]
0x1800281fd  call    cs:__imp_GetCurrentThreadId
0x180028203  mov     rcx, cs:WPP_GLOBAL_Control
0x18002820a  mov     edx, 18h
0x18002820f  mov     r9d, eax
0x180028212  mov     [rsp+50h+var_30], rbx
0x180028217  mov     r8, r12
0x18002821a  mov     rcx, [rcx+10h]
0x18002821e  call    WPP_SF_dS
0x180028223  mov     rax, cs:WPP_GLOBAL_Control
0x18002822a  cmp     rax, r15
0x18002822d  jz      short loc_180028297
0x18002822f  test    [rax+1Ch], r14b
0x180028233  jz      short loc_180028264
0x180028235  mov     ebx, [rbp+arg_8]
0x180028238  call    cs:__imp_GetCurrentThreadId
0x18002823e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028245  mov     edx, 19h
0x18002824a  mov     r9d, eax
0x18002824d  mov     dword ptr [rsp+50h+var_30], ebx
0x180028251  mov     r8, r12
0x180028254  mov     rcx, [rcx+10h]
0x180028258  call    WPP_SF_Dd
0x18002825d  mov     rax, cs:WPP_GLOBAL_Control
0x180028264  cmp     rax, r15
0x180028267  jz      short loc_180028297
0x180028269  test    [rax+1Ch], r14b
0x18002826d  jz      short loc_180028297
0x18002826f  mov     ebx, [rbp+var_20]
0x180028272  call    cs:__imp_GetCurrentThreadId
0x180028278  mov     rcx, cs:WPP_GLOBAL_Control
0x18002827f  mov     edx, 1Ah
0x180028284  mov     r9d, eax
0x180028287  mov     dword ptr [rsp+50h+var_30], ebx
0x18002828b  mov     r8, r12
0x18002828e  mov     rcx, [rcx+10h]
0x180028292  call    WPP_SF_Dd
0x180028297  mov     rcx, [rbp+bstrString]; bstrString
0x18002829b  test    rcx, rcx
0x18002829e  jz      short loc_1800282A6
0x1800282a0  call    cs:__imp_SysFreeString
0x1800282a6  lea     r11, [rsp+50h+var_s0]
0x1800282ab  xor     eax, eax
0x1800282ad  mov     rbx, [r11+30h]
0x1800282b1  mov     rsi, [r11+40h]
0x1800282b5  mov     rsp, r11
0x1800282b8  pop     r15
0x1800282ba  pop     r14
0x1800282bc  pop     r12
0x1800282be  pop     rdi
0x1800282bf  pop     rbp
0x1800282c0  retn
```
