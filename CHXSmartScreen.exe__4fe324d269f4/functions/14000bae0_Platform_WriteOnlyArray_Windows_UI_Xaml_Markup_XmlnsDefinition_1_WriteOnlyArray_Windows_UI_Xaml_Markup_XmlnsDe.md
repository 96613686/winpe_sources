# Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::~WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(void)

- ea: `0x14000bae0`
- end: `0x14000bb4d`
- name: `??1?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@QE$AAA@XZ`
- size: `109`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x14000af84`
- `0x14000afe0`
- `0x14000eac4`

## callees

- `0x1400039b6`
- `0x1400039fe`
- `0x14000bae0`

## pseudocode

```c
void __fastcall Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::~WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
        __int64 a1)
{
  HSTRING *v2; // rsi
  unsigned int v3; // r14d
  unsigned int i; // ebp

  if ( !*(_BYTE *)(a1 + 44) )
  {
    v2 = *(HSTRING **)(a1 + 48);
    if ( v2 )
    {
      v3 = *(_DWORD *)(a1 + 40);
      for ( i = 0; i < v3; ++i )
      {
        WindowsDeleteString_0(v2[2 * i + 1]);
        WindowsDeleteString_0(v2[2 * i]);
      }
      CoTaskMemFree_0(v2);
    }
  }
  *(_DWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 44) = 0;
  *(_QWORD *)(a1 + 48) = 0;
}

```

## disassembly

```asm
0x14000bae0  push    rbx
0x14000bae2  push    rbp
0x14000bae3  push    rsi
0x14000bae4  push    rdi
0x14000bae5  push    r14
0x14000bae7  sub     rsp, 20h
0x14000baeb  cmp     byte ptr [rcx+2Ch], 0
0x14000baef  mov     rdi, rcx
0x14000baf2  jnz     short loc_14000BB2F
0x14000baf4  mov     rsi, [rcx+30h]
0x14000baf8  test    rsi, rsi
0x14000bafb  jz      short loc_14000BB2F
0x14000bafd  mov     r14d, [rcx+28h]
0x14000bb01  xor     ebp, ebp
0x14000bb03  test    r14d, r14d
0x14000bb06  jz      short loc_14000BB27
0x14000bb08  mov     ebx, ebp
0x14000bb0a  add     rbx, rbx
0x14000bb0d  mov     rcx, [rsi+rbx*8+8]; string
0x14000bb12  call    WindowsDeleteString_0
0x14000bb17  mov     rcx, [rsi+rbx*8]; string
0x14000bb1b  call    WindowsDeleteString_0
0x14000bb20  inc     ebp
0x14000bb22  cmp     ebp, r14d
0x14000bb25  jb      short loc_14000BB08
0x14000bb27  mov     rcx, rsi; pv
0x14000bb2a  call    CoTaskMemFree_0
0x14000bb2f  mov     dword ptr [rdi+28h], 0
0x14000bb36  mov     byte ptr [rdi+2Ch], 0
0x14000bb3a  mov     qword ptr [rdi+30h], 0
0x14000bb42  add     rsp, 20h
0x14000bb46  pop     r14
0x14000bb48  pop     rdi
0x14000bb49  pop     rsi
0x14000bb4a  pop     rbp
0x14000bb4b  pop     rbx
0x14000bb4c  retn
```
