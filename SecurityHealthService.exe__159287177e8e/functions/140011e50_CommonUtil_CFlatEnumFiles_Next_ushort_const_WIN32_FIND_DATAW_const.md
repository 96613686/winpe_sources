# CommonUtil::CFlatEnumFiles::Next(ushort const * *,_WIN32_FIND_DATAW const * *)

- ea: `0x140011e50`
- end: `0x140011ee7`
- name: `?Next@CFlatEnumFiles@CommonUtil@@UEAAJPEAPEBGPEAPEBU_WIN32_FIND_DATAW@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(CommonUtil::CFlatEnumFiles *__hidden this, const unsigned __int16 **, const struct _WIN32_FIND_DATAW **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400015f4`
- `0x14000f3ac`
- `0x140011e50`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall CommonUtil::CFlatEnumFiles::Next(
        CommonUtil::CFlatEnumFiles *this,
        const unsigned __int16 **a2,
        const struct _WIN32_FIND_DATAW **a3)
{
  __int64 v3; // rax
  const struct _WIN32_FIND_DATAW **v4; // rdi
  __int64 result; // rax
  const struct _WIN32_FIND_DATAW *v8; // rdi
  void *v9; // rcx
  const unsigned __int16 *v10; // rbp
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF

  v3 = *(_QWORD *)this;
  v4 = (const struct _WIN32_FIND_DATAW **)&v11;
  v11 = 0;
  if ( a3 )
    v4 = a3;
  result = (*(__int64 (__fastcall **)(CommonUtil::CFlatEnumFiles *, const struct _WIN32_FIND_DATAW **))(v3 + 24))(
             this,
             v4);
  if ( (int)result >= 0 )
  {
    v8 = *v4;
    if ( !v8 )
    {
      *a2 = 0;
      return 0;
    }
    v9 = (void *)*((_QWORD *)this + 79);
    v10 = (const unsigned __int16 *)*((_QWORD *)this + 3);
    if ( v9 )
    {
      operator delete(v9);
      *((_QWORD *)this + 79) = 0;
    }
    result = CommonUtil::NewSprintfW(
               (CommonUtil::CFlatEnumFiles *)((char *)this + 632),
               (unsigned __int16 **)L"%ws\\%ws",
               v10,
               (char *)v8->cFileName);
    if ( (int)result >= 0 )
    {
      *a2 = (const unsigned __int16 *)*((_QWORD *)this + 79);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140011e50  push    rbx
0x140011e52  push    rbp
0x140011e53  push    rsi
0x140011e54  push    rdi
0x140011e55  sub     rsp, 28h
0x140011e59  mov     rax, [rcx]
0x140011e5c  lea     rdi, [rsp+48h+arg_0]
0x140011e61  test    r8, r8
0x140011e64  mov     [rsp+48h+arg_0], 0
0x140011e6d  mov     rsi, rdx
0x140011e70  mov     rbx, rcx
0x140011e73  cmovnz  rdi, r8
0x140011e77  mov     rax, [rax+18h]
0x140011e7b  mov     rdx, rdi
0x140011e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e83  test    eax, eax
0x140011e85  js      short loc_140011EDE
0x140011e87  mov     rdi, [rdi]
0x140011e8a  test    rdi, rdi
0x140011e8d  jnz     short loc_140011E94
0x140011e8f  mov     [rsi], rdi
0x140011e92  jmp     short loc_140011EDC
0x140011e94  mov     rcx, [rbx+278h]; void *
0x140011e9b  mov     rbp, [rbx+18h]
0x140011e9f  test    rcx, rcx
0x140011ea2  jz      short loc_140011EB4
0x140011ea4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140011ea9  mov     qword ptr [rbx+278h], 0
0x140011eb4  lea     r9, [rdi+2Ch]
0x140011eb8  mov     r8, rbp; unsigned __int16 *
0x140011ebb  lea     rdx, aWsWs; "%ws\\%ws"
0x140011ec2  lea     rcx, [rbx+278h]; this
0x140011ec9  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x140011ece  test    eax, eax
0x140011ed0  js      short loc_140011EDE
0x140011ed2  mov     rax, [rbx+278h]
0x140011ed9  mov     [rsi], rax
0x140011edc  xor     eax, eax
0x140011ede  add     rsp, 28h
0x140011ee2  pop     rdi
0x140011ee3  pop     rsi
0x140011ee4  pop     rbp
0x140011ee5  pop     rbx
0x140011ee6  retn
```
