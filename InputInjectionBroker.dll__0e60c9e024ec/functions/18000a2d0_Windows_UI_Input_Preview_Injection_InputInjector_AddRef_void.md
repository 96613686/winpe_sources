# Windows::UI::Input::Preview::Injection::InputInjector::AddRef(void)

- ea: `0x18000a2d0`
- end: `0x18000a31e`
- name: `?AddRef@InputInjector@Injection@Preview@Input@UI@Windows@@UEAAKXZ`
- size: `78`
- prototype: `__int64 __fastcall(Windows::UI::Input::Preview::Injection::InputInjector *this)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a330`
- `0x18000a340`
- `0x18000a350`
- `0x18000a360`
- `0x18000a370`

## callees

- `0x18000a2d0`

## pseudocode

```c
__int64 __fastcall Windows::UI::Input::Preview::Injection::InputInjector::AddRef(
        Windows::UI::Input::Preview::Injection::InputInjector *this)
{
  signed __int64 v1; // rdx
  unsigned int v2; // r8d
  unsigned int v3; // r9d
  bool v4; // zf
  signed __int64 v5; // rax
  signed __int32 v6; // r9d

  v1 = *((_QWORD *)this + 10);
  v2 = 0x7FFFFFFF;
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return v2;
    v3 = v1 + 1;
    v5 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 10, v1 + 1, v1);
    v4 = v1 == v5;
    v1 = v5;
    if ( v4 )
      return v3;
  }
  while ( 1 )
  {
    v6 = *(_DWORD *)(2 * v1 + 0x10);
    if ( v6 == 0x7FFFFFFF )
      break;
    if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v6 + 1, v6) )
      return (unsigned int)(v6 + 1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a2d0  mov     rdx, [rcx+50h]
0x18000a2d4  mov     r8d, 7FFFFFFFh
0x18000a2da  test    rdx, rdx
0x18000a2dd  js      short loc_18000A307
0x18000a2df  cmp     edx, r8d
0x18000a2e2  jz      short loc_18000A317
0x18000a2e4  lea     r9, [rdx+1]
0x18000a2e8  mov     rax, rdx
0x18000a2eb  lock cmpxchg [rcx+50h], r9
0x18000a2f1  mov     rdx, rax
0x18000a2f4  jnz     short loc_18000A2DA
0x18000a2f6  jmp     short loc_18000A31A
0x18000a2f8  lea     ecx, [r9+1]
0x18000a2fc  mov     eax, r9d
0x18000a2ff  lock cmpxchg [rdx+rdx+10h], ecx
0x18000a305  jz      short loc_18000A313
0x18000a307  mov     r9d, [rdx+rdx+10h]
0x18000a30c  cmp     r9d, r8d
0x18000a30f  jnz     short loc_18000A2F8
0x18000a311  jmp     short loc_18000A317
0x18000a313  lea     r8d, [r9+1]
0x18000a317  mov     r9d, r8d
0x18000a31a  mov     eax, r9d
0x18000a31d  retn
```
