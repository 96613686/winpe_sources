# CMetadataPngIccpReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x180050270`
- end: `0x180050394`
- name: `?GetValue@CMetadataPngIccpReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004f894`
- `0x180050270`
- `0x1800bd9d4`
- `0x18017e438`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005029f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800502f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050370`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005029f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800502f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180050370`

## pseudocode

```c
__int64 __fastcall CMetadataPngIccpReaderWriter::GetValue(
        CMetadataPngIccpReaderWriter *this,
        int a2,
        struct tagPROPVARIANT *a3)
{
  int v5; // edx
  BYTE *v6; // rax
  unsigned int v7; // ebx
  int v8; // ecx
  char *v10; // rax
  const char *v11; // r8
  unsigned __int64 v12; // rdx
  int v13; // eax
  LONG v14; // eax

  v5 = a2 - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
    {
      v7 = -2147024809;
LABEL_7:
      if ( (_DWORD)g_doStackCaptures )
      {
        v8 = v7;
LABEL_9:
        DoStackCapture(v8);
        return v7;
      }
      return v7;
    }
    if ( *((_QWORD *)this + 21) )
    {
      v6 = (BYTE *)CoTaskMemAlloc(*((_QWORD *)this + 22));
      a3->bstrblobVal.pData = v6;
      if ( !v6 )
      {
LABEL_5:
        v7 = -2147024882;
        goto LABEL_7;
      }
      memcpy_0(v6, *((const void **)this + 21), *((_QWORD *)this + 22));
      v14 = *((_DWORD *)this + 44);
    }
    else
    {
      a3->bstrblobVal.pData = 0;
      v14 = 0;
    }
    v7 = 0;
    a3->lVal = v14;
    return v7;
  }
  if ( *((_QWORD *)this + 19) )
  {
    v10 = (char *)CoTaskMemAlloc(*((_QWORD *)this + 20) + 1LL);
    a3->hVal.QuadPart = (LONGLONG)v10;
    if ( !v10 )
      goto LABEL_5;
    v11 = (const char *)*((_QWORD *)this + 19);
    v12 = *((_QWORD *)this + 20) + 1LL;
  }
  else
  {
    v10 = (char *)CoTaskMemAlloc(0xCu);
    a3->hVal.QuadPart = (LONGLONG)v10;
    if ( !v10 )
      goto LABEL_5;
    v11 = "ICC Profile";
    v12 = 12;
  }
  v13 = StringCchCopyA(v10, v12, v11);
  v7 = v13;
  if ( v13 < 0 && (_DWORD)g_doStackCaptures )
  {
    v8 = v13;
    goto LABEL_9;
  }
  return v7;
}

```

## disassembly

```asm
0x180050270  mov     [rsp+arg_0], rbx
0x180050275  push    rsi
0x180050276  sub     rsp, 20h
0x18005027a  mov     rsi, r8
0x18005027d  mov     rbx, rcx
0x180050280  sub     edx, 1
0x180050283  jz      short loc_1800502E2
0x180050285  cmp     edx, 1
0x180050288  jnz     short loc_1800502BF
0x18005028a  cmp     qword ptr [rcx+0A8h], 0
0x180050292  jz      loc_180050337
0x180050298  mov     rcx, [rcx+0B0h]; cb
0x18005029f  call    cs:__imp_CoTaskMemAlloc
0x1800502a6  nop     dword ptr [rax+rax+00h]
0x1800502ab  mov     [rsi+10h], rax
0x1800502af  test    rax, rax
0x1800502b2  jnz     loc_180050343
0x1800502b8  mov     ebx, 8007000Eh
0x1800502bd  jmp     short loc_1800502C4
0x1800502bf  mov     ebx, 80070057h
0x1800502c4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800502cb  jz      short loc_1800502D4
0x1800502cd  mov     ecx, ebx; int
0x1800502cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800502d4  mov     eax, ebx
0x1800502d6  mov     rbx, [rsp+28h+arg_0]
0x1800502db  add     rsp, 20h
0x1800502df  pop     rsi
0x1800502e0  retn
0x1800502e2  cmp     qword ptr [rcx+98h], 0
0x1800502ea  jz      short loc_180050369
0x1800502ec  mov     rcx, [rcx+0A0h]
0x1800502f3  inc     rcx; cb
0x1800502f6  call    cs:__imp_CoTaskMemAlloc
0x1800502fd  nop     dword ptr [rax+rax+00h]
0x180050302  mov     [rsi+8], rax
0x180050306  test    rax, rax
0x180050309  jz      short loc_1800502B8
0x18005030b  mov     rdx, [rbx+0A0h]
0x180050312  mov     r8, [rbx+98h]; char *
0x180050319  inc     rdx; unsigned __int64
0x18005031c  mov     rcx, rax; char *
0x18005031f  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180050324  mov     ebx, eax
0x180050326  test    eax, eax
0x180050328  jns     short loc_1800502D4
0x18005032a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180050331  jz      short loc_1800502D4
0x180050333  mov     ecx, eax
0x180050335  jmp     short loc_1800502CF
0x180050337  mov     qword ptr [r8+10h], 0
0x18005033f  xor     eax, eax
0x180050341  jmp     short loc_18005035F
0x180050343  mov     r8, [rbx+0B0h]; Size
0x18005034a  mov     rcx, rax; void *
0x18005034d  mov     rdx, [rbx+0A8h]; Src
0x180050354  call    memcpy_0
0x180050359  mov     eax, [rbx+0B0h]
0x18005035f  xor     ebx, ebx
0x180050361  mov     [rsi+8], eax
0x180050364  jmp     loc_1800502D4
0x180050369  mov     ebx, 0Ch
0x18005036e  mov     ecx, ebx; cb
0x180050370  call    cs:__imp_CoTaskMemAlloc
0x180050377  nop     dword ptr [rax+rax+00h]
0x18005037c  mov     [rsi+8], rax
0x180050380  test    rax, rax
0x180050383  jz      loc_1800502B8
0x180050389  lea     r8, aIccProfile_0; "ICC Profile"
0x180050390  mov     edx, ebx
0x180050392  jmp     short loc_18005031C
```
