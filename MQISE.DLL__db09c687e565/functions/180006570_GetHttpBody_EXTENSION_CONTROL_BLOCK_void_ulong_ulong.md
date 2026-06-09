# GetHttpBody(_EXTENSION_CONTROL_BLOCK *,void *,ulong,ulong)

- ea: `0x180006570`
- end: `0x18000676d`
- name: `?GetHttpBody@@YAXPEAU_EXTENSION_CONTROL_BLOCK@@PEAXKK@Z`
- size: `509`
- prototype: `void __fastcall(struct _EXTENSION_CONTROL_BLOCK *, Context *, unsigned int, DWORD)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting`

## callees

- `0x180001c0c`
- `0x180004c7c`
- `0x180006570`
- `0x1800071c4`
- `0x18000c290`
- `0x18000db84`
- `0x18000dbb4`
- `0x180011010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@XZ` at `0x1800066ce`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006711`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006754`
- `msvcrt!??0exception@@QEAA@XZ` at `0x1800066ce`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006711`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180006754`
- `KERNEL32!SetLastError` at `0x180006692`
- `KERNEL32!SetLastError` at `0x180006692`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall GetHttpBody(struct _EXTENSION_CONTROL_BLOCK *a1, Context *a2, unsigned int a3, DWORD a4)
{
  _QWORD *v7; // rdx
  __int64 v8; // r9
  _QWORD *v9; // rax
  __int64 v10; // r8
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // r8
  _BYTE v14[24]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v15[24]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+60h] [rbp-38h] BYREF
  unsigned int v19; // [rsp+B0h] [rbp+18h] BYREF
  int v20; // [rsp+B8h] [rbp+20h] BYREF

  v19 = a3;
  try
  {
    if ( a4 || !a1 || !a2 || (v7 = (_QWORD *)*((_QWORD *)a2 + 1284)) == 0 )
    {
      SetLastError(a4);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, &WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids, a4);
      exception::exception((exception *)pExceptionObject);
      throw (exception *)pExceptionObject;
    }
    v8 = v7[6];
    v9 = v7;
    if ( !v8 )
      v9 = v7 + 1;
    v10 = *v9 + a3;
    if ( v8 )
      *v7 = v10;
    else
      v7[1] = v10;
    v11 = (_QWORD *)*((_QWORD *)a2 + 1284);
    if ( !v11[6] )
      ++v11;
    if ( *v11 >= (unsigned __int64)a1->cbTotalBytes )
    {
      if ( !(unsigned int)HandleEndOfRead(a2, a1) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 19);
        exception::exception((exception *)v15);
        throw (exception *)v15;
      }
      cleanUp(a2);
    }
    else
    {
      v19 = AdjustBuffer(a2, a1);
      v20 = 2;
      v12 = (_QWORD *)*((_QWORD *)a2 + 1284);
      if ( v12[6] )
        v13 = v12[6] + *v12;
      else
        v13 = v12[1] + v12[3];
      if ( !((unsigned int (__fastcall *)(HCONN, __int64, __int64, unsigned int *, int *))a1->ServerSupportFunction)(
              a1->ConnID,
              1010,
              v13,
              &v19,
              &v20) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18);
        exception::exception((exception *)v14);
        throw (exception *)v14;
      }
    }
  }
  catch ( exception )
  {
    SendResponse(a1, "500 Internal server error", 0);
    cleanUp(a2);
  }
}

```

## disassembly

```asm
0x180006570  mov     [rsp+arg_10], r8d
0x180006575  mov     [rsp+arg_8], rdx
0x18000657a  mov     [rsp+arg_0], rcx
0x18000657f  push    rbx
0x180006580  push    rsi
0x180006581  push    rdi
0x180006582  sub     rsp, 80h
0x180006589  mov     esi, r9d
0x18000658c  mov     rbx, rdx
0x18000658f  mov     rdi, rcx
0x180006592  test    r9d, r9d
0x180006595  jnz     loc_180006690
0x18000659b  test    rcx, rcx
0x18000659e  jz      loc_180006690
0x1800065a4  test    rdx, rdx
0x1800065a7  jz      loc_180006690
0x1800065ad  mov     rdx, [rdx+2820h]
0x1800065b4  test    rdx, rdx
0x1800065b7  jz      loc_180006690
0x1800065bd  mov     r9, [rdx+30h]
0x1800065c1  test    r9, r9
0x1800065c4  mov     rax, rdx
0x1800065c7  jnz     short loc_1800065CD
0x1800065c9  lea     rax, [rdx+8]
0x1800065cd  mov     r8d, r8d
0x1800065d0  add     r8, [rax]
0x1800065d3  test    r9, r9
0x1800065d6  jnz     short loc_1800065DE
0x1800065d8  mov     [rdx+8], r8
0x1800065dc  jmp     short loc_1800065E1
0x1800065de  mov     [rdx], r8
0x1800065e1  mov     rcx, [rbx+2820h]
0x1800065e8  lea     rax, [rcx+8]
0x1800065ec  cmp     qword ptr [rcx+30h], 0
0x1800065f1  cmovz   rcx, rax
0x1800065f5  mov     eax, [rdi+88h]
0x1800065fb  mov     rdx, rdi
0x1800065fe  cmp     [rcx], rax
0x180006601  mov     rcx, rbx
0x180006604  jnb     short loc_18000666C
0x180006606  call    AdjustBuffer
0x18000660b  mov     [rsp+98h+arg_10], eax
0x180006612  mov     [rsp+98h+arg_18], 2
0x18000661d  mov     rax, [rbx+2820h]
0x180006624  cmp     qword ptr [rax+30h], 0
0x180006629  jz      short loc_180006634
0x18000662b  mov     r8, [rax]
0x18000662e  add     r8, [rax+30h]
0x180006632  jmp     short loc_18000663C
0x180006634  mov     r8, [rax+18h]
0x180006638  add     r8, [rax+8]
0x18000663c  lea     rax, [rsp+98h+arg_18]
0x180006644  mov     [rsp+98h+var_78], rax
0x180006649  lea     r9, [rsp+98h+arg_10]
0x180006651  mov     edx, 3F2h
0x180006656  mov     rcx, [rdi+8]
0x18000665a  mov     rax, [rdi+0B8h]
0x180006661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006666  test    eax, eax
0x180006668  jz      short loc_1800066E5
0x18000666a  jmp     short loc_180006685
0x18000666c  call    HandleEndOfRead
0x180006671  test    eax, eax
0x180006673  jz      loc_180006728
0x180006679  mov     rdx, rdi
0x18000667c  mov     rcx, rbx; this
0x18000667f  call    cleanUp
0x180006684  nop
0x180006685  add     rsp, 80h
0x18000668c  pop     rdi
0x18000668d  pop     rsi
0x18000668e  pop     rbx
0x18000668f  retn
0x180006690  mov     ecx, esi; dwErrCode
0x180006692  call    cs:__imp_SetLastError
0x180006698  lea     rax, WPP_GLOBAL_Control
0x18000669f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066a6  cmp     rcx, rax
0x1800066a9  jz      short loc_1800066C9
0x1800066ab  test    byte ptr [rcx+6Ch], 1
0x1800066af  jz      short loc_1800066C9
0x1800066b1  mov     edx, 11h
0x1800066b6  mov     r9d, esi
0x1800066b9  lea     r8, WPP_f6c5b0cbaa9434e90ba3dff64f25e7f9_Traceguids
0x1800066c0  mov     rcx, [rcx+60h]
0x1800066c4  call    WPP_SF_d
0x1800066c9  lea     rcx, [rsp+98h+pExceptionObject]
0x1800066ce  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x1800066d4  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x1800066db  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x1800066e0  call    _CxxThrowException_0
0x1800066e5  lea     rax, WPP_GLOBAL_Control
0x1800066ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800066f3  cmp     rcx, rax
0x1800066f6  jz      short loc_18000670C
0x1800066f8  test    byte ptr [rcx+6Ch], 1
0x1800066fc  jz      short loc_18000670C
0x1800066fe  mov     edx, 12h
0x180006703  mov     rcx, [rcx+60h]
0x180006707  call    WPP_SF_
0x18000670c  lea     rcx, [rsp+98h+var_68]
0x180006711  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180006717  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x18000671e  lea     rcx, [rsp+98h+var_68]; pExceptionObject
0x180006723  call    _CxxThrowException_0
0x180006728  lea     rax, WPP_GLOBAL_Control
0x18000672f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006736  cmp     rcx, rax
0x180006739  jz      short loc_18000674F
0x18000673b  test    byte ptr [rcx+6Ch], 1
0x18000673f  jz      short loc_18000674F
0x180006741  mov     edx, 13h
0x180006746  mov     rcx, [rcx+60h]
0x18000674a  call    WPP_SF_
0x18000674f  lea     rcx, [rsp+98h+var_50]
0x180006754  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x18000675a  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180006761  lea     rcx, [rsp+98h+var_50]; pExceptionObject
0x180006766  call    _CxxThrowException_0
```
