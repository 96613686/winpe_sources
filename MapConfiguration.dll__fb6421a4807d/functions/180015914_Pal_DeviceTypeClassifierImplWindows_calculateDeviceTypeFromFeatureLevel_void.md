# Pal::DeviceTypeClassifierImplWindows::calculateDeviceTypeFromFeatureLevel(void)

- ea: `0x180015914`
- end: `0x1800159fe`
- name: `?calculateDeviceTypeFromFeatureLevel@DeviceTypeClassifierImplWindows@Pal@@CA?AW4DeviceType@2@XZ`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015858`

## callees

- `0x180015914`

## import_xrefs

- `d3d11!D3D11CreateDevice` at `0x180015992`
- `d3d11!D3D11CreateDevice` at `0x180015992`

## pseudocode

```c
__int64 Pal::DeviceTypeClassifierImplWindows::calculateDeviceTypeFromFeatureLevel()
{
  D3D_DRIVER_TYPE *v0; // rdi
  unsigned int v1; // ebx
  _DWORD v3[2]; // [rsp+50h] [rbp-18h] BYREF
  char v4; // [rsp+58h] [rbp-10h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevel; // [rsp+70h] [rbp+8h] BYREF
  D3D_FEATURE_LEVEL pFeatureLevels; // [rsp+78h] [rbp+10h] BYREF
  int v7; // [rsp+7Ch] [rbp+14h]

  pFeatureLevel = D3D_FEATURE_LEVEL_11_1;
  pFeatureLevels = D3D_FEATURE_LEVEL_10_0;
  v0 = (D3D_DRIVER_TYPE *)v3;
  v7 = 37120;
  v3[0] = 1;
  v1 = 4;
  v3[1] = 5;
  while ( D3D11CreateDevice(0, *v0, 0, 0x20u, &pFeatureLevels, 2u, 7u, 0, &pFeatureLevel, 0) < 0 )
  {
    if ( ++v0 == (D3D_DRIVER_TYPE *)&v4 )
      return 2;
  }
  if ( pFeatureLevel == D3D_FEATURE_LEVEL_9_1
    || pFeatureLevel == D3D_FEATURE_LEVEL_9_2
    || pFeatureLevel == D3D_FEATURE_LEVEL_9_3 )
  {
    return 1;
  }
  if ( pFeatureLevel != D3D_FEATURE_LEVEL_10_0
    && pFeatureLevel != D3D_FEATURE_LEVEL_10_1
    && pFeatureLevel != D3D_FEATURE_LEVEL_11_0
    && pFeatureLevel != D3D_FEATURE_LEVEL_11_1 )
  {
    return 2;
  }
  return v1;
}

```

## disassembly

```asm
0x180015914  mov     rax, rsp
0x180015917  mov     [rax+18h], rbx
0x18001591b  mov     [rax+20h], rsi
0x18001591f  push    rdi
0x180015920  sub     rsp, 60h
0x180015924  mov     esi, 2
0x180015929  mov     dword ptr [rax+8], 0B100h
0x180015930  mov     dword ptr [rax+10h], 0A000h
0x180015937  lea     rdi, [rax-18h]
0x18001593b  mov     dword ptr [rax+14h], 9100h
0x180015942  mov     dword ptr [rax-18h], 1
0x180015949  lea     ebx, [rsi+2]
0x18001594c  mov     dword ptr [rax-14h], 5
0x180015953  mov     edx, [rdi]; DriverType
0x180015955  lea     rax, [rsp+68h+arg_0]
0x18001595a  mov     [rsp+68h+ppImmediateContext], 0; ppImmediateContext
0x180015963  mov     r9d, 20h ; ' '; Flags
0x180015969  mov     [rsp+68h+pFeatureLevel], rax; pFeatureLevel
0x18001596e  xor     r8d, r8d; Software
0x180015971  mov     [rsp+68h+ppDevice], 0; ppDevice
0x18001597a  lea     rax, [rsp+68h+arg_8]
0x18001597f  mov     [rsp+68h+SDKVersion], 7; SDKVersion
0x180015987  xor     ecx, ecx; pAdapter
0x180015989  mov     [rsp+68h+FeatureLevels], esi; FeatureLevels
0x18001598d  mov     [rsp+68h+pFeatureLevels], rax; pFeatureLevels
0x180015992  call    cs:__imp_D3D11CreateDevice
0x180015998  test    eax, eax
0x18001599a  jns     short loc_1800159AD
0x18001599c  add     rdi, rbx
0x18001599f  lea     rcx, [rsp+68h+var_10]
0x1800159a4  cmp     rdi, rcx
0x1800159a7  jnz     short loc_180015953
0x1800159a9  mov     eax, esi
0x1800159ab  jmp     short loc_1800159EC
0x1800159ad  mov     eax, [rsp+68h+arg_0]
0x1800159b1  cmp     eax, 9100h
0x1800159b6  jz      short loc_1800159E7
0x1800159b8  cmp     eax, 9200h
0x1800159bd  jz      short loc_1800159E7
0x1800159bf  cmp     eax, 9300h
0x1800159c4  jz      short loc_1800159E7
0x1800159c6  cmp     eax, 0A000h
0x1800159cb  jz      short loc_1800159E3
0x1800159cd  cmp     eax, 0A100h
0x1800159d2  jz      short loc_1800159E3
0x1800159d4  cmp     eax, 0B000h
0x1800159d9  jz      short loc_1800159E3
0x1800159db  cmp     eax, 0B100h
0x1800159e0  cmovnz  ebx, esi
0x1800159e3  mov     eax, ebx
0x1800159e5  jmp     short loc_1800159EC
0x1800159e7  mov     eax, 1
0x1800159ec  lea     r11, [rsp+68h+var_8]
0x1800159f1  mov     rbx, [r11+20h]
0x1800159f5  mov     rsi, [r11+28h]
0x1800159f9  mov     rsp, r11
0x1800159fc  pop     rdi
0x1800159fd  retn
```
