# CUpdateDeploymentJob::FindIndex2ById(tagDSGlobalUpdateId const &,ulong,ulong *)

- ea: `0x1800365c4`
- end: `0x180036724`
- name: `?FindIndex2ById@CUpdateDeploymentJob@@AEAAJAEBUtagDSGlobalUpdateId@@KPEAK@Z`
- size: `352`
- prototype: `int(CUpdateDeploymentJob *__hidden this, const struct tagDSGlobalUpdateId *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030988`
- `0x180035ca0`

## callees

- `0x180003180`
- `0x18000c640`
- `0x1800365c4`
- `0x180061960`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x180036627`
- `RPCRT4!UuidToStringW` at `0x180036627`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800366b9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800366b9`

## string_xrefs

- `0x1800365f8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x180036646`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::FindIndex2ById(
        CUpdateDeploymentJob *this,
        const UUID *a2,
        unsigned int a3,
        unsigned int *a4)
{
  __int64 v4; // rsi
  unsigned int v8; // ebx
  RPC_STATUS v9; // eax
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // r13
  unsigned __int16 *v13; // r8
  int lpString2; // [rsp+20h] [rbp-58h]
  RPC_WSTR StringUuid; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = a3;
  if ( a4 )
  {
    StringUuid = 0;
    v9 = UuidToStringW(a2, &StringUuid);
    v8 = v9;
    if ( v9 >= 1 )
      v8 = (unsigned __int16)v9 | 0x80010000;
    if ( (v8 & 0x80000000) == 0 )
    {
      *a4 = -1;
      v10 = 0;
      v11 = *((_QWORD *)this + 87);
      if ( *(_DWORD *)(*(_QWORD *)(v11 + 8 * v4) + 544LL) )
      {
        while ( 1 )
        {
          v12 = *(_QWORD *)(v11 + 8 * v4);
          v13 = *(unsigned __int16 **)(*(_QWORD *)(*(_QWORD *)(v12 + 552) + 8 * v10) + 16LL);
          if ( (v13 == StringUuid || v13 && StringUuid && CompareStringW(0x7Fu, 1u, v13, -1, StringUuid, -1) == 2)
            && *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v12 + 552) + 8 * v10) + 24LL) == a2[1].Data1 )
          {
            break;
          }
          v11 = *((_QWORD *)this + 87);
          v10 = (unsigned int)(v10 + 1);
          if ( (unsigned int)v10 >= *(_DWORD *)(*(_QWORD *)(v11 + 8 * v4) + 544LL) )
            goto LABEL_14;
        }
        *a4 = v10;
        v8 = 0;
      }
      else
      {
LABEL_14:
        v8 = -2145120257;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x182D,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
        (const char *)v8,
        lpString2);
    }
    if ( StringUuid )
      XPtrRpcStringFree(StringUuid);
  }
  else
  {
    v8 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1828,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80004003LL,
      lpString2);
  }
  return v8;
}

```

## disassembly

```asm
0x1800365c4  push    rbx
0x1800365c6  push    rbp
0x1800365c7  push    rsi
0x1800365c8  push    rdi
0x1800365c9  push    r13
0x1800365cb  push    r14
0x1800365cd  push    r15
0x1800365cf  sub     rsp, 40h
0x1800365d3  mov     rax, cs:__security_cookie
0x1800365da  xor     rax, rsp
0x1800365dd  mov     [rsp+78h+var_40], rax
0x1800365e2  mov     esi, r8d
0x1800365e5  mov     rdi, r9
0x1800365e8  mov     rbp, rdx
0x1800365eb  mov     r14, rcx
0x1800365ee  test    r9, r9
0x1800365f1  jnz     short loc_180036616
0x1800365f3  mov     rcx, [rsp+78h]; this
0x1800365f8  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800365ff  mov     ebx, 80004003h
0x180036604  mov     edx, 1828h; void *
0x180036609  mov     r9d, ebx; char *
0x18003660c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036611  jmp     loc_180036700
0x180036616  lea     rdx, [rsp+78h+StringUuid]; StringUuid
0x18003661b  mov     [rsp+78h+StringUuid], 0
0x180036624  mov     rcx, rbp; Uuid
0x180036627  call    cs:__imp_UuidToStringW
0x18003662d  mov     ebx, eax
0x18003662f  cmp     eax, 1
0x180036632  jl      short loc_18003663D
0x180036634  movzx   ebx, ax
0x180036637  or      ebx, 80010000h
0x18003663d  test    ebx, ebx
0x18003663f  jns     short loc_18003665F
0x180036641  mov     rcx, [rsp+78h]; this
0x180036646  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x18003664d  mov     r9d, ebx; char *
0x180036650  mov     edx, 182Dh; void *
0x180036655  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003665a  jmp     loc_1800366F1
0x18003665f  mov     dword ptr [rdi], 0FFFFFFFFh
0x180036665  xor     ebx, ebx
0x180036667  mov     rcx, [r14+2B8h]
0x18003666e  mov     rax, [rcx+rsi*8]
0x180036672  cmp     [rax+220h], ebx
0x180036678  jbe     short loc_1800366EC
0x18003667a  mov     r13, [rcx+rsi*8]
0x18003667e  mov     rdx, [rsp+78h+StringUuid]
0x180036683  mov     rax, [r13+228h]
0x18003668a  mov     rcx, [rax+rbx*8]
0x18003668e  mov     r8, [rcx+10h]; lpString1
0x180036692  cmp     r8, rdx
0x180036695  jz      short loc_1800366C4
0x180036697  test    r8, r8
0x18003669a  jz      short loc_1800366D7
0x18003669c  test    rdx, rdx
0x18003669f  jz      short loc_1800366D7
0x1800366a1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800366a5  mov     [rsp+78h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800366ad  mov     [rsp+78h+lpString2], rdx; lpString2
0x1800366b2  lea     edx, [r9+2]; dwCmpFlags
0x1800366b6  lea     ecx, [rdx+7Eh]; Locale
0x1800366b9  call    cs:__imp_CompareStringW
0x1800366bf  cmp     eax, 2
0x1800366c2  jnz     short loc_1800366D7
0x1800366c4  mov     rax, [r13+228h]
0x1800366cb  mov     rcx, [rax+rbx*8]
0x1800366cf  mov     eax, [rbp+10h]
0x1800366d2  cmp     [rcx+18h], eax
0x1800366d5  jz      short loc_18003671E
0x1800366d7  mov     rcx, [r14+2B8h]
0x1800366de  inc     ebx
0x1800366e0  mov     rax, [rcx+rsi*8]
0x1800366e4  cmp     ebx, [rax+220h]
0x1800366ea  jb      short loc_18003667A
0x1800366ec  mov     ebx, 80240FFFh
0x1800366f1  mov     rcx, [rsp+78h+StringUuid]; void *
0x1800366f6  test    rcx, rcx
0x1800366f9  jz      short loc_180036700
0x1800366fb  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180036700  mov     eax, ebx
0x180036702  mov     rcx, [rsp+78h+var_40]
0x180036707  xor     rcx, rsp; StackCookie
0x18003670a  call    __security_check_cookie
0x18003670f  add     rsp, 40h
0x180036713  pop     r15
0x180036715  pop     r14
0x180036717  pop     r13
0x180036719  pop     rdi
0x18003671a  pop     rsi
0x18003671b  pop     rbp
0x18003671c  pop     rbx
0x18003671d  retn
0x18003671e  mov     [rdi], ebx
0x180036720  xor     ebx, ebx
0x180036722  jmp     short loc_1800366F1
```
