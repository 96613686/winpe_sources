# AsyncPipe::ReadCompletedCallback(void)

- ea: `0x14000d744`
- end: `0x14000d812`
- name: `?ReadCompletedCallback@AsyncPipe@@AEAAXXZ`
- size: `206`
- prototype: `void __fastcall(_DWORD *pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d6c0`

## callees

- `0x14000d744`
- `0x14000da74`
- `0x14000e1b4`
- `0x140012010`

## string_xrefs

- `0x14000d780`: `ReadFile %u`

## pseudocode

```c
void __fastcall AsyncPipe::ReadCompletedCallback(_DWORD *pv)
{
  int v1; // r9d
  __int64 v3; // rcx

  v1 = pv[62];
  if ( v1 )
  {
    if ( v1 == 6 || v1 == 109 || v1 == 232 || v1 == 233 )
    {
LABEL_11:
      v3 = *((_QWORD *)pv + 4);
      goto LABEL_15;
    }
    if ( v1 != 995 )
    {
      if ( v1 != 1223 )
      {
        __FatalError((const char *)pv, 492, "ReadFile %u", v1);
        goto LABEL_17;
      }
      goto LABEL_11;
    }
    if ( *((_QWORD *)pv + 3) == -1 )
      goto LABEL_17;
LABEL_13:
    AsyncPipe::StartRead((char *)pv);
    goto LABEL_17;
  }
  (*(void (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)pv + 4) + 24LL))(
    *((_QWORD *)pv + 4),
    (char *)pv + 260,
    (unsigned int)pv[64]);
  if ( *((_QWORD *)pv + 3) != -1 )
    goto LABEL_13;
  v3 = *((_QWORD *)pv + 4);
LABEL_15:
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 32LL))(v3);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)pv + 4) + 16LL))(*((_QWORD *)pv + 4));
    *((_QWORD *)pv + 4) = 0;
  }
LABEL_17:
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)pv + 24LL))(pv);
}

```

## disassembly

```asm
0x14000d744  push    rbx
0x14000d746  sub     rsp, 20h
0x14000d74a  mov     r9d, [rcx+0F8h]; unsigned int
0x14000d751  mov     rbx, rcx
0x14000d754  mov     edx, r9d
0x14000d757  test    r9d, r9d
0x14000d75a  jz      short loc_14000D7A2
0x14000d75c  sub     edx, 6
0x14000d75f  jz      short loc_14000D79C
0x14000d761  sub     edx, 67h ; 'g'
0x14000d764  jz      short loc_14000D79C
0x14000d766  sub     edx, 7Bh ; '{'
0x14000d769  jz      short loc_14000D79C
0x14000d76b  sub     edx, 1
0x14000d76e  jz      short loc_14000D79C
0x14000d770  sub     edx, 2FAh
0x14000d776  jz      short loc_14000D793
0x14000d778  cmp     edx, 0E4h
0x14000d77e  jz      short loc_14000D79C
0x14000d780  lea     r8, aReadfileU; "ReadFile %u"
0x14000d787  mov     edx, 1ECh; unsigned int
0x14000d78c  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x14000d791  jmp     short loc_14000D7FE
0x14000d793  cmp     qword ptr [rcx+18h], 0FFFFFFFFFFFFFFFFh
0x14000d798  jnz     short loc_14000D7C7
0x14000d79a  jmp     short loc_14000D7FE
0x14000d79c  mov     rcx, [rcx+20h]
0x14000d7a0  jmp     short loc_14000D7D5
0x14000d7a2  mov     rcx, [rcx+20h]
0x14000d7a6  lea     rdx, [rbx+104h]
0x14000d7ad  mov     r8d, [rbx+100h]
0x14000d7b4  mov     rax, [rcx]
0x14000d7b7  mov     rax, [rax+18h]
0x14000d7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7c0  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x14000d7c5  jz      short loc_14000D7D1
0x14000d7c7  mov     rcx, rbx; pv
0x14000d7ca  call    ?StartRead@AsyncPipe@@AEAAXXZ; AsyncPipe::StartRead(void)
0x14000d7cf  jmp     short loc_14000D7FE
0x14000d7d1  mov     rcx, [rbx+20h]
0x14000d7d5  test    rcx, rcx
0x14000d7d8  jz      short loc_14000D7FE
0x14000d7da  mov     rax, [rcx]
0x14000d7dd  mov     rax, [rax+20h]
0x14000d7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7e6  mov     rcx, [rbx+20h]
0x14000d7ea  mov     rax, [rcx]
0x14000d7ed  mov     rax, [rax+10h]
0x14000d7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7f6  mov     qword ptr [rbx+20h], 0
0x14000d7fe  mov     rax, [rbx]
0x14000d801  mov     rcx, rbx
0x14000d804  mov     rax, [rax+18h]
0x14000d808  add     rsp, 20h
0x14000d80c  pop     rbx
0x14000d80d  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
