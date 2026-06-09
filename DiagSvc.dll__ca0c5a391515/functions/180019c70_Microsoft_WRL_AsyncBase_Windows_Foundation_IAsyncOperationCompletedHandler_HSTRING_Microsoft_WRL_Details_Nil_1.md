# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)

- ea: `0x180019c70`
- end: `0x180019cd2`
- name: `?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800168c0`
- `0x180016af0`
- `0x1800177a0`
- `0x180017890`
- `0x180019a00`
- `0x180019d04`
- `0x18001a1e4`

## callees

- `0x180019c70`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
        __int64 a1,
        signed __int32 a2)
{
  signed __int32 v2; // r8d
  signed __int32 v4; // ecx
  signed __int32 v6; // [rsp+10h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v6 = -2;
  _InterlockedCompareExchange(&v6, v2, -2);
  switch ( a2 )
  {
    case 0:
      v4 = v6;
      if ( v6 != -1 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 1:
    case 2:
    case 3:
      v4 = v6;
      if ( v6 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 4:
      v4 = v6;
      if ( (unsigned int)(v6 - 1) <= 3 )
        return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180019c70  mov     r8d, [rcx+38h]
0x180019c74  mov     r9, rcx
0x180019c77  mov     [rsp+arg_8], 0FFFFFFFEh
0x180019c7f  mov     eax, [rsp+arg_8]
0x180019c83  lock cmpxchg [rsp+arg_8], r8d
0x180019c8a  mov     eax, edx
0x180019c8c  test    edx, edx
0x180019c8e  jz      short loc_180019CC6
0x180019c90  sub     eax, 1
0x180019c93  jz      short loc_180019CBC
0x180019c95  sub     eax, 1
0x180019c98  jz      short loc_180019CBC
0x180019c9a  sub     eax, 1
0x180019c9d  jz      short loc_180019CBC
0x180019c9f  cmp     eax, 1
0x180019ca2  jnz     short loc_180019CCF
0x180019ca4  mov     ecx, [rsp+arg_8]
0x180019ca8  lea     eax, [rcx-1]
0x180019cab  cmp     eax, 3
0x180019cae  ja      short loc_180019CCF
0x180019cb0  mov     eax, ecx
0x180019cb2  lock cmpxchg [r9+38h], edx
0x180019cb8  setz    al
0x180019cbb  retn
0x180019cbc  mov     ecx, [rsp+arg_8]
0x180019cc0  test    ecx, ecx
0x180019cc2  jnz     short loc_180019CCF
0x180019cc4  jmp     short loc_180019CB0
0x180019cc6  mov     ecx, [rsp+arg_8]
0x180019cca  cmp     ecx, 0FFFFFFFFh
0x180019ccd  jz      short loc_180019CB0
0x180019ccf  xor     al, al
0x180019cd1  retn
```
