# CMsMpComFactory::CreateNativeInstance(_GUID const &,IUnknown * *)

- ea: `0x180003b30`
- end: `0x180003c6e`
- name: `?CreateNativeInstance@CMsMpComFactory@@UEAAJAEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `318`
- prototype: `__int64 __fastcall(unsigned __int64 this, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002920`
- `0x180002a60`
- `0x180003b30`
- `0x180004b54`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall CMsMpComFactory::CreateNativeInstance(
        unsigned __int64 this,
        const struct _GUID *a2,
        struct IUnknown **a3)
{
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  if ( *(_BYTE *)(this + 32) )
  {
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMsMpComFactory.Data1
      && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMsMpComFactory.Data4
      || *(_QWORD *)&a2->Data1 == 0x403D0109AC30C2BALL && *(_QWORD *)a2->Data4 == 0x9C3770B40B148E9DuLL )
    {
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)this + 8LL))(this);
      *a3 = (struct IUnknown *)(this & -(__int64)(this != 64));
      return 0;
    }
    else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMsMpClientUtils.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMsMpClientUtils.Data4
           || *(_QWORD *)&a2->Data1 == 0x460E8E41E2D74550LL && *(_QWORD *)a2->Data4 == 0x342152F9E15251BBLL )
    {
      return MpCoCreateUnknownComObject_CMsMpClientUtils_(a3);
    }
    else if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IMsMpSimpleConfig.Data1
           && *(_QWORD *)a2->Data4 == *(_QWORD *)IID_IMsMpSimpleConfig.Data4
           || *(_QWORD *)&a2->Data1 == 0x43097999CDFED399LL && *(_QWORD *)a2->Data4 == 0xD58BC04DE1E64B0LL )
    {
      return MpCoCreateUnknownComObject_CMsMpSimpleConfig_(a3);
    }
    else
    {
      return 2147500034LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids);
    return 2147942405LL;
  }
}

```

## disassembly

```asm
0x180003b30  mov     [rsp+arg_0], rbx
0x180003b35  push    rdi
0x180003b36  sub     rsp, 20h
0x180003b3a  mov     rbx, r8
0x180003b3d  mov     rdi, rcx
0x180003b40  test    r8, r8
0x180003b43  jnz     short loc_180003B4F
0x180003b45  mov     eax, 80004003h
0x180003b4a  jmp     loc_180003C63
0x180003b4f  mov     qword ptr [r8], 0
0x180003b56  cmp     byte ptr [rcx+20h], 0
0x180003b5a  jnz     short loc_180003B94
0x180003b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b63  lea     rax, WPP_GLOBAL_Control
0x180003b6a  cmp     rcx, rax
0x180003b6d  jz      short loc_180003B8A
0x180003b6f  test    byte ptr [rcx+1Ch], 1
0x180003b73  jz      short loc_180003B8A
0x180003b75  mov     rcx, [rcx+10h]
0x180003b79  lea     r8, WPP_142e9f78c9ff30724e8ad65b92a2bbe6_Traceguids
0x180003b80  mov     edx, 0Ah
0x180003b85  call    WPP_SF_
0x180003b8a  mov     eax, 80070005h
0x180003b8f  jmp     loc_180003C63
0x180003b94  mov     rax, [rdx]
0x180003b97  cmp     rax, qword ptr cs:IID_IMsMpComFactory.Data1
0x180003b9e  jnz     short loc_180003BAD
0x180003ba0  mov     rax, [rdx+8]
0x180003ba4  cmp     rax, qword ptr cs:IID_IMsMpComFactory.Data4
0x180003bab  jz      short loc_180003BC6
0x180003bad  mov     rax, [rdx]
0x180003bb0  cmp     rax, cs:qword_18000D320
0x180003bb7  jnz     short loc_180003BE6
0x180003bb9  mov     rax, [rdx+8]
0x180003bbd  cmp     rax, cs:qword_18000D328
0x180003bc4  jnz     short loc_180003BE6
0x180003bc6  mov     rax, [rcx]
0x180003bc9  mov     rax, [rax+8]
0x180003bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003bd2  lea     rax, [rdi-40h]
0x180003bd6  neg     rax
0x180003bd9  sbb     rcx, rcx
0x180003bdc  and     rcx, rdi
0x180003bdf  mov     [rbx], rcx
0x180003be2  xor     eax, eax
0x180003be4  jmp     short loc_180003C63
0x180003be6  mov     rax, [rdx]
0x180003be9  cmp     rax, qword ptr cs:IID_IMsMpClientUtils.Data1
0x180003bf0  jnz     short loc_180003BFF
0x180003bf2  mov     rax, [rdx+8]
0x180003bf6  cmp     rax, qword ptr cs:IID_IMsMpClientUtils.Data4
0x180003bfd  jz      short loc_180003C18
0x180003bff  mov     rax, [rdx]
0x180003c02  cmp     rax, cs:qword_18000D310
0x180003c09  jnz     short loc_180003C22
0x180003c0b  mov     rax, [rdx+8]
0x180003c0f  cmp     rax, cs:qword_18000D318
0x180003c16  jnz     short loc_180003C22
0x180003c18  mov     rcx, rbx
0x180003c1b  call    MpCoCreateUnknownComObject_CMsMpClientUtils_
0x180003c20  jmp     short loc_180003C63
0x180003c22  mov     rax, [rdx]
0x180003c25  cmp     rax, qword ptr cs:IID_IMsMpSimpleConfig.Data1
0x180003c2c  jnz     short loc_180003C3B
0x180003c2e  mov     rax, [rdx+8]
0x180003c32  cmp     rax, qword ptr cs:IID_IMsMpSimpleConfig.Data4
0x180003c39  jz      short loc_180003C54
0x180003c3b  mov     rax, [rdx]
0x180003c3e  cmp     rax, cs:qword_18000D300
0x180003c45  jnz     short loc_180003C5E
0x180003c47  mov     rax, [rdx+8]
0x180003c4b  cmp     rax, cs:qword_18000D308
0x180003c52  jnz     short loc_180003C5E
0x180003c54  mov     rcx, rbx
0x180003c57  call    MpCoCreateUnknownComObject_CMsMpSimpleConfig_
0x180003c5c  jmp     short loc_180003C63
0x180003c5e  mov     eax, 80004002h
0x180003c63  mov     rbx, [rsp+28h+arg_0]
0x180003c68  add     rsp, 20h
0x180003c6c  pop     rdi
0x180003c6d  retn
```
