# BackgroundExecutionSessionClient::AddRef(void)

- ea: `0x180003460`
- end: `0x18000349d`
- name: `?AddRef@BackgroundExecutionSessionClient@@UEAAKXZ`
- size: `61`
- prototype: `unsigned int __fastcall(BackgroundExecutionSessionClient *this, volatile int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800051e0`
- `0x1800051f0`
- `0x180005200`

## callees

- `0x180003460`
- `0x180004320`

## pseudocode

```c
unsigned int __fastcall BackgroundExecutionSessionClient::AddRef(
        BackgroundExecutionSessionClient *this,
        volatile int *a2)
{
  signed __int64 v2; // rax
  signed __int64 v3; // rtt

  v2 = *((_QWORD *)this + 8);
  while ( 1 )
  {
    if ( v2 < 0 )
      return Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      break;
    a2 = (volatile int *)(v2 + 1);
    v3 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 8, v2 + 1, v2);
    if ( v3 == v2 )
      return (unsigned int)a2;
  }
  return 0x7FFFFFFF;
}

```

## disassembly

```asm
0x180003460  sub     rsp, 28h
0x180003464  mov     rax, [rcx+40h]
0x180003468  test    rax, rax
0x18000346b  js      short loc_180003487
0x18000346d  cmp     eax, 7FFFFFFFh
0x180003472  jz      short loc_180003496
0x180003474  lea     rdx, [rax+1]; volatile int *
0x180003478  lock cmpxchg [rcx+40h], rdx
0x18000347e  jnz     short loc_180003468
0x180003480  mov     eax, edx
0x180003482  add     rsp, 28h
0x180003486  retn
0x180003487  lea     rcx, ds:10h[rax*2]; this
0x18000348f  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180003494  jmp     short loc_180003482
0x180003496  mov     eax, 7FFFFFFFh
0x18000349b  jmp     short loc_180003482
```
