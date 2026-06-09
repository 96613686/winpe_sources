# Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::.cctor

- ea: `0x2d430`
- end: `0x2d495`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::.cctor`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x2d430`: `Opening the package for processing`
- `0x2d458`: `Vsix does not have signature to create certificate file`
- `0x2d48a`: `Unable to create certificateInformation.dat. The vsix package does not chain to a trusted root.`

## pseudocode

```c

```

## disassembly

```asm
0x2d430  ldstr    aOpeningThePack// "Opening the package for processing"
0x2d435  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::ExtractionOpenPackage
0x2d43a  ldstr    aGettingListOfF// "Getting list of files within the packag"...
0x2d43f  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::ExtractionQueryParts
0x2d444  ldstr    aProcessingFile// "Processing file {0}"
0x2d449  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::PartProcessing
0x2d44e  ldstr    aCreatingVsixCe// "Creating vsix certificateInformation.da"...
0x2d453  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::CreateVsixCertFileText
0x2d458  ldstr    aVsixDoesNotHav// "Vsix does not have signature to create "...
0x2d45d  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::MissingVsixCertFileText
0x2d462  ldstr    aDeletingVsixCe// "Deleting Vsix certificateInformation.da"...
0x2d467  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::VsixCertFileExistsText
0x2d46c  ldstr    aUnableToGetSub// "Unable to get subject name from Vsix si"...
0x2d471  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::VsixSubjectNameMissing
0x2d476  ldstr    aExceptionDelet// "Exception deleting Vsix certificateInfo"...
0x2d47b  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::ExceptionDeletingVsixCertFileText
0x2d480  ldstr    aExceptionCreat_0// "Exception creating Vsix certificateInfo"...
0x2d485  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::ExceptionCreatingVsixCertFileText
0x2d48a  ldstr    aUnableToCreate_1// "Unable to create certificateInformation"...
0x2d48f  stsfld   string Microsoft.VisualStudio.Setup.Installer.InstallerDiagnosticMessages::VsixIncompleteCertChain
0x2d494  ret
```
