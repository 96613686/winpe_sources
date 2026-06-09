# Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(long)

- ea: `0x1800b7e3c`
- end: `0x1800b802a`
- name: `?ValidateDeviceApiCall@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAAXJ@Z`
- size: `494`
- prototype: `void __fastcall(Spectre::Engine::D3D11::RenderDeviceD3D11 *__hidden this, int)`
- caller_count: `35`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800ba8f0`
- `0x1800bb040`
- `0x1800bb3e0`
- `0x1800bbd50`
- `0x1800bbf8c`
- `0x1800bd164`
- `0x1800bd744`
- `0x1800bdb80`
- `0x1800bddc4`
- `0x1800be080`
- `0x1800bea74`
- `0x1800bf6e0`
- `0x1800bf980`
- `0x1800bfd0c`
- `0x1800c0790`
- `0x1800c1ff0`
- `0x1800c2510`
- `0x1800c2b94`
- `0x1800c2d60`
- `0x1800c31b4`
- `0x1800c3b80`
- `0x1800c3f40`
- `0x1800c4710`
- `0x1800c4f90`
- `0x1800c5428`
- `0x1800c56d0`
- `0x1800c61b0`
- `0x1800c63f0`
- `0x1800c6640`
- `0x1800c6890`
- `0x1800c6bd0`
- `0x1800c6dd0`
- `0x1800c6fd0`
- `0x1800c7508`
- `0x1800c767c`

## callees

- `0x180012c88`
- `0x18001d578`
- `0x18001daf4`
- `0x1800b64c4`
- `0x1800b7e3c`
- `0x1800e7010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800b8014`
- `msvcp_win!_Mtx_unlock` at `0x1800b8014`

## string_xrefs

- `0x1800b7f10`: `ValidateDeviceAPICAll: Device removed because it was reset.`
- `0x1800b7f36`: `ValidateDeviceAPICAll: Device removed. Possibly because new drivers were installed?`
- `0x1800b7f49`: `ValidateDeviceAPICAll: Device removed because of invalid call. Likely error in our code.`
- `0x1800b7f01`: `ValidateDeviceAPICAll: Device removed because of driver internal error.`
- `0x1800b7f23`: `ValidateDeviceAPICAll: Device removed because it hung.`
- `0x1800b7eeb`: `ValidateDeviceAPICAll: Device removed but reason was S_OK. Better device now available?`
- `0x1800b7f5c`: `ValidateDeviceAPICAll: Device removed and is now null so cannot be queried. Serious error.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Spectre::Engine::D3D11::RenderDeviceD3D11::ValidateDeviceApiCall(
        Spectre::Engine::D3D11::RenderDeviceD3D11 *this,
        int a2)
{
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rax
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF
  char *v7; // [rsp+40h] [rbp+18h]

  if ( !*((_DWORD *)this + 1062) )
  {
    *((_DWORD *)this + 1063) = a2;
    if ( a2 )
    {
      switch ( a2 )
      {
        case -2005270523:
          v3 = *((_QWORD *)this + 532);
          if ( v3 )
          {
            v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 312LL))(v3);
            switch ( v4 )
            {
              case -2005270527:
                *((_DWORD *)this + 1062) = 5;
                Trace::LevelSettingsWrapper::Output(
                  &gTraceLevelsNativeRenderer_RendererD3D11,
                  3,
                  "ValidateDeviceAPICAll: Device removed because of invalid call. Likely error in our code.");
                break;
              case -2005270523:
                *((_DWORD *)this + 1062) = 2;
                Trace::LevelSettingsWrapper::Output(
                  &gTraceLevelsNativeRenderer_RendererD3D11,
                  3,
                  "ValidateDeviceAPICAll: Device removed. Possibly because new drivers were installed?");
                break;
              case -2005270522:
                *((_DWORD *)this + 1062) = 1;
                Trace::LevelSettingsWrapper::Output(
                  &gTraceLevelsNativeRenderer_RendererD3D11,
                  3,
                  "ValidateDeviceAPICAll: Device removed because it hung.");
                break;
              case -2005270521:
                *((_DWORD *)this + 1062) = 3;
                Trace::LevelSettingsWrapper::Output(
                  &gTraceLevelsNativeRenderer_RendererD3D11,
                  3,
                  "ValidateDeviceAPICAll: Device removed because it was reset.");
                break;
              case -2005270496:
                *((_DWORD *)this + 1062) = 4;
                Trace::LevelSettingsWrapper::Output(
                  &gTraceLevelsNativeRenderer_RendererD3D11,
                  3,
                  "ValidateDeviceAPICAll: Device removed because of driver internal error.");
                break;
              default:
                if ( v4 )
                {
                  *((_DWORD *)this + 1062) = 2;
                }
                else
                {
                  *((_DWORD *)this + 1062) = 0;
                  Trace::LevelSettingsWrapper::Output(
                    &gTraceLevelsNativeRenderer_RendererD3D11,
                    3,
                    "ValidateDeviceAPICAll: Device removed but reason was S_OK. Better device now available?");
                }
                break;
            }
          }
          else
          {
            *((_DWORD *)this + 1062) = 2;
            Trace::LevelSettingsWrapper::Output(
              &gTraceLevelsNativeRenderer_RendererD3D11,
              3,
              "ValidateDeviceAPICAll: Device removed and is now null so cannot be queried. Serious error.");
          }
          break;
        case -2005270521:
          *((_DWORD *)this + 1062) = 3;
          Trace::LevelSettingsWrapper::Output(
            &gTraceLevelsNativeRenderer_RendererD3D11,
            3,
            "ValidateDeviceAPICAll: Device was reset.");
          break;
        case -2147024882:
          Trace::LevelSettingsWrapper::Output(
            &gTraceLevelsNativeRenderer_RendererD3D11,
            3,
            "ValidateDeviceAPICAll: Device out of memory. Calling OOM callbacks.");
          Spectre::Engine::D3D11::RenderDeviceD3D11::HandleOutOfMemory(this);
          break;
      }
    }
    else
    {
      *((_DWORD *)this + 1062) = 0;
    }
    if ( *((_DWORD *)this + 1062) )
    {
      Trace::LevelSettingsWrapper::Output(
        &gTraceLevelsNativeRenderer_RendererD3D11,
        3,
        "ValidateDeviceAPICAll: Calling Device-lost callback to notify clients.");
      v7 = (char *)this + 4168;
      std::_Mutex_base::lock((Spectre::Engine::D3D11::RenderDeviceD3D11 *)((char *)this + 4168));
      v5 = **((_QWORD **)this + 519);
      v6 = v5;
      while ( !*(_BYTE *)(v5 + 25) )
      {
        (***(void (__fastcall ****)(_QWORD, _QWORD))(v5 + 32))(*(_QWORD *)(v5 + 32), *((unsigned int *)this + 1062));
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<enum Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(&v6);
        v5 = v6;
      }
      _Mtx_unlock((Spectre::Engine::D3D11::RenderDeviceD3D11 *)((char *)this + 4168));
    }
  }
}

```

## disassembly

```asm
0x1800b7e3c  mov     [rsp+arg_8], rbx
0x1800b7e41  mov     [rsp+arg_18], rsi
0x1800b7e46  push    rdi
0x1800b7e47  sub     rsp, 20h
0x1800b7e4b  mov     rdi, rcx
0x1800b7e4e  cmp     dword ptr [rcx+1098h], 0
0x1800b7e55  jnz     loc_1800B801A
0x1800b7e5b  mov     [rcx+109Ch], edx
0x1800b7e61  mov     ebx, 3
0x1800b7e66  lea     rsi, ?gTraceLevelsNativeRenderer_RendererD3D11@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_RendererD3D11
0x1800b7e6d  test    edx, edx
0x1800b7e6f  jnz     short loc_1800B7E7C
0x1800b7e71  mov     [rcx+1098h], edx
0x1800b7e77  jmp     loc_1800B7FA7
0x1800b7e7c  cmp     edx, 887A0005h
0x1800b7e82  jnz     loc_1800B7F65
0x1800b7e88  mov     rcx, [rcx+10A0h]
0x1800b7e8f  test    rcx, rcx
0x1800b7e92  jz      loc_1800B7F52
0x1800b7e98  mov     rax, [rcx]
0x1800b7e9b  mov     rax, [rax+138h]
0x1800b7ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ea7  cmp     eax, 887A0001h
0x1800b7eac  jz      loc_1800B7F3F
0x1800b7eb2  cmp     eax, 887A0005h
0x1800b7eb7  jz      short loc_1800B7F2C
0x1800b7eb9  cmp     eax, 887A0006h
0x1800b7ebe  jz      short loc_1800B7F19
0x1800b7ec0  cmp     eax, 887A0007h
0x1800b7ec5  jz      short loc_1800B7F0A
0x1800b7ec7  cmp     eax, 887A0020h
0x1800b7ecc  jz      short loc_1800B7EF7
0x1800b7ece  test    eax, eax
0x1800b7ed0  jz      short loc_1800B7EE1
0x1800b7ed2  mov     dword ptr [rdi+1098h], 2
0x1800b7edc  jmp     loc_1800B7FA7
0x1800b7ee1  mov     dword ptr [rdi+1098h], 0
0x1800b7eeb  lea     r8, aValidatedevice_0; "ValidateDeviceAPICAll: Device removed b"...
0x1800b7ef2  jmp     loc_1800B7F7A
0x1800b7ef7  mov     dword ptr [rdi+1098h], 4
0x1800b7f01  lea     r8, aValidatedevice_6; "ValidateDeviceAPICAll: Device removed b"...
0x1800b7f08  jmp     short loc_1800B7F7A
0x1800b7f0a  mov     [rdi+1098h], ebx
0x1800b7f10  lea     r8, aValidatedevice_8; "ValidateDeviceAPICAll: Device removed b"...
0x1800b7f17  jmp     short loc_1800B7F7A
0x1800b7f19  mov     dword ptr [rdi+1098h], 1
0x1800b7f23  lea     r8, aValidatedevice_5; "ValidateDeviceAPICAll: Device removed b"...
0x1800b7f2a  jmp     short loc_1800B7F7A
0x1800b7f2c  mov     dword ptr [rdi+1098h], 2
0x1800b7f36  lea     r8, aValidatedevice_2; "ValidateDeviceAPICAll: Device removed. "...
0x1800b7f3d  jmp     short loc_1800B7F7A
0x1800b7f3f  mov     dword ptr [rdi+1098h], 5
0x1800b7f49  lea     r8, aValidatedevice; "ValidateDeviceAPICAll: Device removed b"...
0x1800b7f50  jmp     short loc_1800B7F7A
0x1800b7f52  mov     dword ptr [rdi+1098h], 2
0x1800b7f5c  lea     r8, aValidatedevice_3; "ValidateDeviceAPICAll: Device removed a"...
0x1800b7f63  jmp     short loc_1800B7F7A
0x1800b7f65  cmp     edx, 887A0007h
0x1800b7f6b  jnz     short loc_1800B7F86
0x1800b7f6d  mov     [rcx+1098h], ebx
0x1800b7f73  lea     r8, aValidatedevice_1; "ValidateDeviceAPICAll: Device was reset"...
0x1800b7f7a  mov     edx, ebx
0x1800b7f7c  mov     rcx, rsi
0x1800b7f7f  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1800b7f84  jmp     short loc_1800B7FA7
0x1800b7f86  cmp     edx, 8007000Eh
0x1800b7f8c  jnz     short loc_1800B7FA7
0x1800b7f8e  lea     r8, aValidatedevice_4; "ValidateDeviceAPICAll: Device out of me"...
0x1800b7f95  mov     edx, ebx
0x1800b7f97  mov     rcx, rsi
0x1800b7f9a  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1800b7f9f  mov     rcx, rdi; this
0x1800b7fa2  call    ?HandleOutOfMemory@RenderDeviceD3D11@D3D11@Engine@Spectre@@IEAA_NXZ; Spectre::Engine::D3D11::RenderDeviceD3D11::HandleOutOfMemory(void)
0x1800b7fa7  cmp     dword ptr [rdi+1098h], 0
0x1800b7fae  jz      short loc_1800B801A
0x1800b7fb0  lea     r8, aValidatedevice_7; "ValidateDeviceAPICAll: Calling Device-l"...
0x1800b7fb7  mov     edx, ebx
0x1800b7fb9  mov     rcx, rsi
0x1800b7fbc  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1800b7fc1  lea     rbx, [rdi+1048h]
0x1800b7fc8  mov     [rsp+28h+arg_10], rbx
0x1800b7fcd  mov     rcx, rbx; this
0x1800b7fd0  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800b7fd5  nop
0x1800b7fd6  mov     rax, [rdi+1038h]
0x1800b7fdd  mov     rax, [rax]
0x1800b7fe0  mov     [rsp+28h+arg_0], rax
0x1800b7fe5  cmp     byte ptr [rax+19h], 0
0x1800b7fe9  jnz     short loc_1800B8011
0x1800b7feb  mov     rcx, [rax+20h]
0x1800b7fef  mov     rax, [rcx]
0x1800b7ff2  mov     edx, [rdi+1098h]
0x1800b7ff8  mov     rax, [rax]
0x1800b7ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8000  lea     rcx, [rsp+28h+arg_0]
0x1800b8005  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4RenderDeviceID@Engine@Spectre@@V?$shared_ptr@VDeviceConstantBuffer@Engine@Spectre@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<Spectre::Engine::RenderDeviceID const,std::shared_ptr<Spectre::Engine::DeviceConstantBuffer>>>>,std::_Iterator_base0>::operator++(void)
0x1800b800a  mov     rax, [rsp+28h+arg_0]
0x1800b800f  jmp     short loc_1800B7FE5
0x1800b8011  mov     rcx, rbx; _Mtx_t
0x1800b8014  call    cs:__imp__Mtx_unlock
0x1800b801a  mov     rbx, [rsp+28h+arg_8]
0x1800b801f  mov     rsi, [rsp+28h+arg_18]
0x1800b8024  add     rsp, 20h
0x1800b8028  pop     rdi
0x1800b8029  retn
```
