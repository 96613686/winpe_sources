# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::InternalRelease(void)

- ea: `0x18000ee90`
- end: `0x18000eed9`
- name: `?InternalRelease@?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@WRL@Microsoft@@IEAAKXZ`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c870`

## callees

- `0x18000ee90`
- `0x180010760`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::InternalRelease(__int64 *a1)
{
  unsigned int v2; // [rsp+20h] [rbp-18h]
  __int64 v3; // [rsp+28h] [rbp-10h]

  v2 = 0;
  v3 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return (unsigned int)Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(v3);
  }
  return v2;
}

```

## disassembly

```asm
0x18000ee90  mov     [rsp+arg_0], rcx
0x18000ee95  sub     rsp, 38h
0x18000ee99  mov     [rsp+38h+var_18], 0
0x18000eea1  mov     rax, [rsp+38h+arg_0]
0x18000eea6  mov     rax, [rax]
0x18000eea9  mov     [rsp+38h+var_10], rax
0x18000eeae  cmp     [rsp+38h+var_10], 0
0x18000eeb4  jz      short loc_18000EED0
0x18000eeb6  mov     rax, [rsp+38h+arg_0]
0x18000eebb  mov     qword ptr [rax], 0
0x18000eec2  mov     rcx, [rsp+38h+var_10]
0x18000eec7  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18000eecc  mov     [rsp+38h+var_18], eax
0x18000eed0  mov     eax, [rsp+38h+var_18]
0x18000eed4  add     rsp, 38h
0x18000eed8  retn
```
