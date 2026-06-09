# CCreateDescriptorHeapValidator::Validate(D3D12_DESCRIPTOR_HEAP_DESC const *,D3D12_RESOURCE_BINDING_TIER,CDevice *)

- ea: `0x18002c940`
- end: `0x18002cab9`
- name: `?Validate@CCreateDescriptorHeapValidator@@QEAAJPEBUD3D12_DESCRIPTOR_HEAP_DESC@@W4D3D12_RESOURCE_BINDING_TIER@@PEAVCDevice@@@Z`
- size: `377`
- prototype: `__int64 __fastcall(CCreateDescriptorHeapValidator *__hidden this, const struct D3D12_DESCRIPTOR_HEAP_DESC *, enum D3D12_RESOURCE_BINDING_TIER, struct CDevice *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002cac0`

## callees

- `0x18002c940`
- `0x18002ef50`
- `0x180076fec`

## string_xrefs

- `0x18002caad`: `D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, device supports D3D12_RESOURCE_BINDING_TIER_1 which limits shader visible descriptor heap size to %d.`
- `0x18002ca8f`: `D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, but the limit for shader visible view heaps is %d`
- `0x18023375b`: `D3D12_DESCRIPTOR_HEAP_DESC.Flags cannot include D3D12_DESCRIPTOR_HEAP_FLAG_SHADER_VISIBLE when D3D12_DESCRIPTOR_HEAP_DESC.Type is D3D12_DESCRIPTOR_HEAP_TYPE_RTV or D3D12_DESCRIPTOR_HEAP_TYPE_DSV.`
- `0x18002c9fa`: `D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, device supports D3D12_RESOURCE_BINDING_TIER_2 which limits shader visible descriptor heap size to %d.`
- `0x18002ca78`: `D3D12_DESCRIPTOR_HEAP_DESC.Type set to %d - invalid desciptor heap type. `
- `0x180233786`: `D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, but the limit for shader visible sampler heaps is %d `
- `0x18002ca43`: `D3D12_DESCRIPTOR_HEAP_DESC.Flags - invalid flags, must be 0 or D3D12_DESCRIPTOR_HEAP_FLAG_SHADER_VISIBLE. `

## pseudocode

```c
__int64 __fastcall CCreateDescriptorHeapValidator::Validate(
        CCreateDescriptorHeapValidator *this,
        const struct D3D12_DESCRIPTOR_HEAP_DESC *a2,
        enum D3D12_RESOURCE_BINDING_TIER a3,
        struct CDevice *a4)
{
  int v4; // eax
  int v5; // ebx
  D3D12_DESCRIPTOR_HEAP_TYPE Type; // r9d
  int v11; // esi
  const char *v12; // r8
  const char *v13; // r8
  __int64 v14; // rdx

  v4 = *((_DWORD *)a4 + 76);
  v5 = 0;
  if ( v4 == 256 )
  {
    if ( a2->Type == D3D12_DESCRIPTOR_HEAP_TYPE_CBV_SRV_UAV )
      goto LABEL_3;
    v13 = "This operation is not supported on a generic device.";
    v14 = 1381;
    goto LABEL_26;
  }
  if ( v4 == 4096 )
  {
    this = (CCreateDescriptorHeapValidator *)(unsigned int)a2->Type;
    if ( (unsigned int)((_DWORD)this - 2) <= 1 || (_DWORD)this == 1 )
    {
      v13 = "This operation is not supported on a core device.";
      v14 = 1157;
LABEL_26:
      v5 = 1;
      TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, v14, v13);
    }
  }
LABEL_3:
  if ( (a2->Flags & 0xFFFFFFFE) != 0 )
  {
    ++v5;
    TDebugOutputFunctor::operator()(
      &g_coreRuntimeTallyErrorOutputFunctor,
      645,
      "D3D12_DESCRIPTOR_HEAP_DESC.Flags - invalid flags, must be 0 or D3D12_DESCRIPTOR_HEAP_FLAG_SHADER_VISIBLE. ");
  }
  if ( (a2->Flags & 1) != 0 )
  {
    Type = a2->Type;
    if ( a2->Type )
    {
      if ( Type == D3D12_DESCRIPTOR_HEAP_TYPE_SAMPLER )
      {
        if ( a2->NumDescriptors <= *((_DWORD *)a4 + 443) )
          return v5 != 0 ? 0x80070057 : 0;
        v12 = "D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, but the limit for shader visible sampler heaps is %d ";
        goto LABEL_31;
      }
      if ( (unsigned int)(Type - 2) < 2 )
      {
        if ( !CDevice::EarlyAdopterBehavior(this) )
        {
          ++v5;
          TDebugOutputFunctor::operator()(
            &g_coreRuntimeTallyErrorOutputFunctor,
            645,
            "D3D12_DESCRIPTOR_HEAP_DESC.Flags cannot include D3D12_DESCRIPTOR_HEAP_FLAG_SHADER_VISIBLE when D3D12_DESCRIP"
            "TOR_HEAP_DESC.Type is D3D12_DESCRIPTOR_HEAP_TYPE_RTV or D3D12_DESCRIPTOR_HEAP_TYPE_DSV.");
        }
      }
      else
      {
        ++v5;
        TDebugOutputFunctor::operator()(
          &g_coreRuntimeTallyErrorOutputFunctor,
          645,
          "D3D12_DESCRIPTOR_HEAP_DESC.Type set to %d - invalid desciptor heap type. ",
          Type);
      }
    }
    else
    {
      if ( (*((_BYTE *)a4 + 1480) & 8) != 0 )
      {
        if ( a2->NumDescriptors <= *((_DWORD *)a4 + 445) )
          return v5 != 0 ? 0x80070057 : 0;
        v12 = "D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, but the limit for shader visible view heaps is %d";
LABEL_31:
        ++v5;
        TDebugOutputFunctor::operator()(&g_coreRuntimeTallyErrorOutputFunctor, 645, v12);
        return v5 != 0 ? 0x80070057 : 0;
      }
      v11 = a3 - 1;
      if ( !v11 )
      {
        if ( a2->NumDescriptors <= 0xF4240 )
          return v5 != 0 ? 0x80070057 : 0;
        v12 = "D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, device supports D3D12_RESOURCE_BINDING_TIER_1 which limits s"
              "hader visible descriptor heap size to %d.";
        goto LABEL_31;
      }
      if ( v11 == 1 && a2->NumDescriptors > 0xF4240 )
      {
        v12 = "D3D12_DESCRIPTOR_HEAP_DESC.NumDescriptors %d, device supports D3D12_RESOURCE_BINDING_TIER_2 which limits s"
              "hader visible descriptor heap size to %d.";
        goto LABEL_31;
      }
    }
  }
  return v5 != 0 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x18002c940  push    rbx
0x18002c942  push    rbp
0x18002c943  push    rsi
0x18002c944  push    rdi
0x18002c945  push    r12
0x18002c947  push    r14
0x18002c949  push    r15
0x18002c94b  sub     rsp, 30h
0x18002c94f  mov     eax, [r9+130h]
0x18002c956  lea     r15, ?g_coreRuntimeTallyErrorOutputFunctor@@3UTDebugOutputFunctor@@A; TDebugOutputFunctor g_coreRuntimeTallyErrorOutputFunctor
0x18002c95d  xor     ebx, ebx
0x18002c95f  mov     rbp, r9
0x18002c962  mov     esi, r8d
0x18002c965  mov     rdi, rdx
0x18002c968  lea     r14d, [rbx+1]
0x18002c96c  cmp     eax, 100h
0x18002c971  jz      loc_18002CA06
0x18002c977  cmp     eax, 1000h
0x18002c97c  jz      loc_18002CA1F
0x18002c982  test    dword ptr [rdi+8], 0FFFFFFFEh
0x18002c989  mov     r12d, 285h
0x18002c98f  jnz     loc_18002CA40
0x18002c995  test    [rdi+8], r14b
0x18002c999  jz      short loc_18002C9C6
0x18002c99b  mov     r9d, [rdi]
0x18002c99e  mov     r8d, r9d
0x18002c9a1  test    r9d, r9d
0x18002c9a4  jnz     loc_18002CA5A
0x18002c9aa  test    byte ptr [rbp+5C8h], 8
0x18002c9b1  jz      short loc_18002C9DE
0x18002c9b3  mov     eax, [rbp+6F4h]
0x18002c9b9  mov     r9d, [rdi+4]
0x18002c9bd  cmp     r9d, eax
0x18002c9c0  ja      loc_18002CA8F
0x18002c9c6  neg     ebx
0x18002c9c8  sbb     eax, eax
0x18002c9ca  and     eax, 80070057h
0x18002c9cf  add     rsp, 30h
0x18002c9d3  pop     r15
0x18002c9d5  pop     r14
0x18002c9d7  pop     r12
0x18002c9d9  pop     rdi
0x18002c9da  pop     rsi
0x18002c9db  pop     rbp
0x18002c9dc  pop     rbx
0x18002c9dd  retn
0x18002c9de  sub     esi, r14d
0x18002c9e1  jz      loc_18002CA9B
0x18002c9e7  cmp     esi, r14d
0x18002c9ea  jnz     short loc_18002C9C6
0x18002c9ec  mov     r9d, [rdi+4]
0x18002c9f0  mov     eax, 0F4240h
0x18002c9f5  cmp     r9d, eax
0x18002c9f8  jbe     short loc_18002C9C6
0x18002c9fa  lea     r8, aD3d12Descripto_0; "D3D12_DESCRIPTOR_HEAP_DESC.NumDescripto"...
0x18002ca01  jmp     loc_18023378D
0x18002ca06  cmp     [rdx], ebx
0x18002ca08  jz      loc_18002C982
0x18002ca0e  lea     r8, aThisOperationI_0; "This operation is not supported on a ge"...
0x18002ca15  mov     edx, 565h
0x18002ca1a  jmp     loc_18023373A
0x18002ca1f  mov     ecx, [rdx]
0x18002ca21  lea     eax, [rcx-2]
0x18002ca24  cmp     eax, r14d
0x18002ca27  setbe   al
0x18002ca2a  test    al, al
0x18002ca2c  jnz     loc_18023372E
0x18002ca32  cmp     ecx, r14d
0x18002ca35  jnz     loc_18002C982
0x18002ca3b  jmp     loc_18023372E
0x18002ca40  add     ebx, r14d
0x18002ca43  lea     r8, aD3d12Descripto_2; "D3D12_DESCRIPTOR_HEAP_DESC.Flags - inva"...
0x18002ca4a  mov     edx, r12d
0x18002ca4d  mov     rcx, r15
0x18002ca50  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18002ca55  jmp     loc_18002C995
0x18002ca5a  sub     r8d, r14d
0x18002ca5d  jz      loc_180233773
0x18002ca63  sub     r8d, r14d
0x18002ca66  jz      loc_18023374B
0x18002ca6c  cmp     r8d, r14d
0x18002ca6f  jz      loc_18023374B
0x18002ca75  add     ebx, r14d
0x18002ca78  lea     r8, aD3d12Descripto_4; "D3D12_DESCRIPTOR_HEAP_DESC.Type set to "...
0x18002ca7f  mov     edx, r12d
0x18002ca82  mov     rcx, r15
0x18002ca85  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18002ca8a  jmp     loc_18002C9C6
0x18002ca8f  lea     r8, aD3d12Descripto; "D3D12_DESCRIPTOR_HEAP_DESC.NumDescripto"...
0x18002ca96  jmp     loc_18023378D
0x18002ca9b  mov     r9d, [rdi+4]
0x18002ca9f  mov     eax, 0F4240h
0x18002caa4  cmp     r9d, eax
0x18002caa7  jbe     loc_18002C9C6
0x18002caad  lea     r8, aD3d12Descripto_3; "D3D12_DESCRIPTOR_HEAP_DESC.NumDescripto"...
0x18002cab4  jmp     loc_18023378D
0x18023372e  lea     r8, aThisOperationI_1; "This operation is not supported on a co"...
0x180233735  mov     edx, 485h
0x18023373a  mov     rcx, r15
0x18023373d  mov     ebx, r14d
0x180233740  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180233745  nop
0x180233746  jmp     loc_18002C982
0x18023374b  call    ?EarlyAdopterBehavior@CDevice@@QEBA_NXZ; CDevice::EarlyAdopterBehavior(void)
0x180233750  test    al, al
0x180233752  jnz     loc_18002C9C6
0x180233758  add     ebx, r14d
0x18023375b  lea     r8, aD3d12Descripto_5; "D3D12_DESCRIPTOR_HEAP_DESC.Flags cannot"...
0x180233762  mov     edx, r12d
0x180233765  mov     rcx, r15
0x180233768  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18023376d  nop
0x18023376e  jmp     loc_18002C9C6
0x180233773  mov     eax, [rbp+6ECh]
0x180233779  mov     r9d, [rdi+4]
0x18023377d  cmp     r9d, eax
0x180233780  jbe     loc_18002C9C6
0x180233786  lea     r8, aD3d12Descripto_1; "D3D12_DESCRIPTOR_HEAP_DESC.NumDescripto"...
0x18023378d  add     ebx, r14d
0x180233790  mov     [rsp+68h+var_48], eax
0x180233794  mov     edx, r12d
0x180233797  mov     rcx, r15
0x18023379a  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x18023379f  nop
0x1802337a0  jmp     loc_18002C9C6
```
