# MapsStorageGetDataDirectory(HMAPSSTORAGE__ *,ushort *,ulong)

- ea: `0x18000fc60`
- end: `0x18000fccb`
- name: `?MapsStorageGetDataDirectory@@YAJPEAUHMAPSSTORAGE__@@PEAGK@Z`
- size: `107`
- prototype: `__int64 __fastcall(struct HMAPSSTORAGE__ *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x18000895c`
- `0x18000fc60`

## pseudocode

```c
__int64 __fastcall MapsStorageGetDataDirectory(struct HMAPSSTORAGE__ *a1, unsigned __int16 *a2)
{
  int v2; // ebx
  __int64 v3; // rdx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
  {
    v2 = -2147467261;
    v3 = 200;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\mapsstorageclient.cpp",
      (const char *)(unsigned int)v2,
      v5);
    return (unsigned int)v2;
  }
  v2 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short *,unsigned long),void * &,unsigned short * &,unsigned long &>();
  if ( v2 < 0 )
  {
    v3 = 205;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000fc60  mov     [rsp+arg_10], r8d
0x18000fc65  mov     [rsp+arg_8], rdx
0x18000fc6a  push    rbx; int
0x18000fc6b  sub     rsp, 20h
0x18000fc6f  test    rdx, rdx
0x18000fc72  jnz     short loc_18000FC96
0x18000fc74  mov     ebx, 80004003h
0x18000fc79  mov     edx, 0C8h; void *
0x18000fc7e  mov     rcx, [rsp+28h]; this
0x18000fc83  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000fc8a  mov     r9d, ebx; char *
0x18000fc8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fc92  mov     eax, ebx
0x18000fc94  jmp     short loc_18000FCC5
0x18000fc96  mov     [rsp+28h+arg_18], rcx
0x18000fc9b  lea     r9, [rsp+28h+arg_10]
0x18000fca0  lea     rcx, MapsStorageSvcGetDataDirectory
0x18000fca7  lea     r8, [rsp+28h+arg_8]
0x18000fcac  lea     rdx, [rsp+28h+arg_18]
0x18000fcb1  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@wil@@YAJA6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &>(long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &)
0x18000fcb6  mov     ebx, eax
0x18000fcb8  test    eax, eax
0x18000fcba  jns     short loc_18000FCC3
0x18000fcbc  mov     edx, 0CDh
0x18000fcc1  jmp     short loc_18000FC7E
0x18000fcc3  xor     eax, eax
0x18000fcc5  add     rsp, 20h
0x18000fcc9  pop     rbx
0x18000fcca  retn
```
