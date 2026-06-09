# CMetadataPngIccpReaderWriter::GetValue(uint,tagPROPVARIANT *)

- ea: `0x1800af160`
- end: `0x1800af271`
- name: `?GetValue@CMetadataPngIccpReaderWriter@@MEAAJIPEAUtagPROPVARIANT@@@Z`
- size: `273`
- prototype: `__int64 __fastcall(CMetadataPngIccpReaderWriter *__hidden this, unsigned int, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180020e14`
- `0x1800af160`
- `0x1800bb784`
- `0x18017b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af18f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af1df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af253`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af18f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af1df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800af253`

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
0x1800af160  mov     [rsp+arg_0], rbx
0x1800af165  push    rsi
0x1800af166  sub     rsp, 20h
0x1800af16a  mov     rsi, r8
0x1800af16d  mov     rbx, rcx
0x1800af170  sub     edx, 1
0x1800af173  jz      short loc_1800AF1CB
0x1800af175  cmp     edx, 1
0x1800af178  jnz     short loc_1800AF1A9
0x1800af17a  cmp     qword ptr [rcx+0A8h], 0
0x1800af182  jz      loc_1800AF21A
0x1800af188  mov     rcx, [rcx+0B0h]; cb
0x1800af18f  call    cs:__imp_CoTaskMemAlloc
0x1800af195  mov     [rsi+10h], rax
0x1800af199  test    rax, rax
0x1800af19c  jnz     loc_1800AF226
0x1800af1a2  mov     ebx, 8007000Eh
0x1800af1a7  jmp     short loc_1800AF1AE
0x1800af1a9  mov     ebx, 80070057h
0x1800af1ae  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800af1b5  jz      short loc_1800AF1BE
0x1800af1b7  mov     ecx, ebx; int
0x1800af1b9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800af1be  mov     eax, ebx
0x1800af1c0  mov     rbx, [rsp+28h+arg_0]
0x1800af1c5  add     rsp, 20h
0x1800af1c9  pop     rsi
0x1800af1ca  retn
0x1800af1cb  cmp     qword ptr [rcx+98h], 0
0x1800af1d3  jz      short loc_1800AF24C
0x1800af1d5  mov     rcx, [rcx+0A0h]
0x1800af1dc  inc     rcx; cb
0x1800af1df  call    cs:__imp_CoTaskMemAlloc
0x1800af1e5  mov     [rsi+8], rax
0x1800af1e9  test    rax, rax
0x1800af1ec  jz      short loc_1800AF1A2
0x1800af1ee  mov     rdx, [rbx+0A0h]
0x1800af1f5  mov     r8, [rbx+98h]; char *
0x1800af1fc  inc     rdx; unsigned __int64
0x1800af1ff  mov     rcx, rax; char *
0x1800af202  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800af207  mov     ebx, eax
0x1800af209  test    eax, eax
0x1800af20b  jns     short loc_1800AF1BE
0x1800af20d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800af214  jz      short loc_1800AF1BE
0x1800af216  mov     ecx, eax
0x1800af218  jmp     short loc_1800AF1B9
0x1800af21a  mov     qword ptr [r8+10h], 0
0x1800af222  xor     eax, eax
0x1800af224  jmp     short loc_1800AF242
0x1800af226  mov     r8, [rbx+0B0h]; Size
0x1800af22d  mov     rcx, rax; void *
0x1800af230  mov     rdx, [rbx+0A8h]; Src
0x1800af237  call    memcpy_0
0x1800af23c  mov     eax, [rbx+0B0h]
0x1800af242  xor     ebx, ebx
0x1800af244  mov     [rsi+8], eax
0x1800af247  jmp     loc_1800AF1BE
0x1800af24c  mov     ebx, 0Ch
0x1800af251  mov     ecx, ebx; cb
0x1800af253  call    cs:__imp_CoTaskMemAlloc
0x1800af259  mov     [rsi+8], rax
0x1800af25d  test    rax, rax
0x1800af260  jz      loc_1800AF1A2
0x1800af266  lea     r8, aIccProfile_0; "ICC Profile"
0x1800af26d  mov     edx, ebx
0x1800af26f  jmp     short loc_1800AF1FF
```
